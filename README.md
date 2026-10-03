# DeliverPuyo Frontend

Aplicación móvil de delivery desarrollada con Flutter y Dart. Permite consultar el catálogo, autenticarse y gestionar el flujo de pedidos mediante la API REST de DeliverPuyo.

## Tecnologías

- Flutter / Dart
- Riverpod y GoRouter
- Dio para HTTP
- Almacenamiento seguro de sesión
- Android, iOS, Web, Windows, Linux y macOS

## Estructura

- `lib/`: autenticación, catálogo, pedidos, direcciones, navegación y UI.
- `android/`, `ios/`, `web/`, `windows/`, `linux/`, `macos/`: plataformas Flutter.
- `test/`, `integration_test/`: pruebas unitarias e integración.
- `pubspec.yaml`, `pubspec.lock`: dependencias fijadas.

## Requisitos

- Flutter stable 3.44.4 o compatible con el SDK declarado en `pubspec.yaml`.
- Un dispositivo/emulador Android para pruebas móviles.

## Instalación y validación

Desde la raíz de este repositorio:

```sh
flutter pub get
flutter analyze
flutter test
```

## Ejecutar contra producción

```sh
flutter run --dart-define=API_URL=https://deliverpuyo-backend.onrender.com --dart-define=AMBIENTE=prod
```

El cliente exige HTTPS cuando `AMBIENTE=prod`. Flutter móvil nativo no depende de CORS. Flutter Web requiere que su origen esté permitido por la configuración CORS del backend.

La firma release de Android usa un keystore local fuera del repositorio y `android/key.properties`, ignorado por Git. No subas el keystore ni ese archivo.

Consulta `docs/CONTRATO_API.md` para el contrato de consumo de la API.
