# InterfazCarApp

Aplicación Flutter diseñada como una interfaz moderna de alquiler y reserva de autos. La app presenta una pantalla principal con búsqueda, marcas destacadas, vehículos más alquilados y un detalle del coche seleccionado con información relevante como precio, potencia, pasajeros y equipaje.

La interfaz está construida con un estilo visual premium, colores sobrios, cards con esquinas redondeadas, tipografía elegante y componentes reutilizables para ofrecer una experiencia de usuario visualmente cuidada y coherente.

## ¿Qué hace la aplicación?

La app simula una experiencia de compra/alquiler de vehículos con estas funcionalidades principales:

- Pantalla de inicio con encabezado, búsqueda y presentación visual de marcas.
- Catalogo horizontal de vehículos “más alquilados”.
- Tarjetas de autos con nombre, categoría, precio por día y vista previa de la imagen.
- Navegación a una pantalla detallada del vehículo seleccionado.
- Vista de detalles del coche con:
  - potencia
  - capacidad de personas
  - capacidad de maletero
  - rating
  - precio por día
  - selección de ubicación
- Uso de transiciones fluidas y estilos visuales adaptados a mobile.

## Arquitectura del proyecto

El proyecto sigue una estructura simple y clara para una app de UI de Flutter:

- lib/main.dart:
  - punto de entrada de la aplicación
  - configura `GetMaterialApp`
  - define el theme principal y la pantalla inicial

- lib/screens/
  - `home_screen.dart`: pantalla principal con búsqueda, marcas y lista de autos disponibles
  - `card_screen.dart`: pantalla de detalle del coche con información ampliada

- lib/model/
  - `car_model.dart`: catálogo estático de autos con datos como nombre, clase, precio, imagen y métricas

- lib/share/
  - `components.dart`: widgets reutilizables como cards, barras de navegación, botones, inputs y componentes visuales compartidos

- assets/
  - imágenes de coches, iconos de marcas y recursos visuales para la interfaz

## Estructura del proyecto

```text
InterfazCarApp/
├── android/
├── ios/
├── assets/
│   ├── app-icon.png
│   ├── hyundai_logo.png
│   ├── volkswagen_logo.png
│   ├── toyota_logo.png
│   ├── bmw_logo.png
│   ├── i30n_car.png
│   ├── golf_car.png
│   └── yaris_car.png
├── lib/
│   ├── main.dart
│   ├── model/
│   │   └── car_model.dart
│   ├── screens/
│   │   ├── home_screen.dart
│   │   └── card_screen.dart
│   └── share/
│       └── components.dart
├── test/
├── .gitignore
├── .metadata
├── analysis_options.yaml
├── pubspec.lock
├── pubspec.yaml
├── README.md
└── screenshots/
```

## Paquetes principales

La app utiliza los siguientes paquetes en `pubspec.yaml`:

- `flutter`: SDK principal de Flutter.
- `cupertino_icons`: iconos estilo iOS.
- `google_fonts`: tipografías personalizadas para mejorar la identidad visual.
- `get`: librería para navegación, estado y transiciones (`GetMaterialApp`, `Get.to(...)`).
- `unicons`: conjunto de iconos modernos para UI.
- `flutter_launcher_icons`: para generar iconos de la aplicación.

También usa una configuración de Material 3 con `useMaterial3: true`.

## Dependencias y configuración

El archivo `pubspec.yaml` define la aplicación como `car_app_ui` y establece las dependencias principales. La configuración actual indica que el proyecto requiere:

- Flutter SDK: `>=2.19.0 <3.0.0`
- versión de la app: `1.0.0+1`

La aplicación carga recursos desde `assets/` y usa imágenes locales para mostrar marcas y modelos disponibles.

## Flujo de la aplicación

El flujo principal es el siguiente:

1. La app inicia en `main.dart`.
2. Se crea un `GetMaterialApp` con la pantalla principal.
3. `HomePage` renderiza la interfaz inicial con:
   - barra superior
   - input de búsqueda
   - marcas top
   - vehículos más alquilados
4. Al tocar un vehículo, se navega a `CardPage`.
5. En la pantalla de detalle se muestran datos del coche, precio y una sección de ubicación.

## Cómo ejecutar la aplicación

Requisitos:

- Flutter instalado y configurado en tu máquina.
- Android Studio / VS Code con emulador o dispositivo físico conectado.
- Acceso a internet para descargar dependencias del pub.

Pasos:

```bash
git clone https://github.com/YaelHuerta1/InterfazCarApp.git
cd InterfazCarApp
flutter pub get
flutter run
```

Si quieres ejecutar en un dispositivo específico:

```bash
flutter devices
flutter run -d <device_id>
```

## Recomendaciones de desarrollo

- Mantener la estructura por capas (`model`, `screens`, `share`) para que la UI sea más escalable.
- Si se amplía el proyecto, conviene migrar los datos del modelo a una capa de datos o servicio real.
- Para un proyecto más mantenible, se recomienda separar aún más widgets complejos en carpetas como `widgets`, `controllers` y `routes`.

## Conclusión

`InterfazCarApp` es una interfaz de usuario móvil para un servicio de alquiler de vehículos, con un enfoque visual moderno y una navegación clara entre catálogo y detalle. El proyecto demuestra cómo construir una UI elegante en Flutter usando recursos locales, tipografías personalizadas, iconografía moderna y componentes reutilizables.

Es un excelente punto de partida para proyectos de movilidad, booking de autos o cualquier aplicación de marketplace con enfoque visual premium.
