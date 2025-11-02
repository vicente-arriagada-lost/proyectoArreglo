# GameZone - Aplicación Android de Tienda de Videojuegos

## Descripción General
GameZone es una aplicación Android nativa construida con Kotlin y Jetpack Compose. La app funciona como una tienda de videojuegos donde los usuarios pueden registrarse, iniciar sesión, explorar juegos y agregar productos al carrito.

## Tipo de Proyecto
**Aplicación Móvil Android** - Este proyecto está diseñado para ejecutarse en dispositivos Android o emuladores, no en navegadores web.

## Stack Tecnológico
- **Lenguaje**: Kotlin 2.0.21
- **Sistema de Build**: Gradle 8.13.0
- **Framework UI**: Jetpack Compose
- **Arquitectura**: MVVM (Model-View-ViewModel)
- **SDK Android Mínimo**: 24 (Android 7.0)
- **SDK Android Target**: 34 (Android 14)
- **Bibliotecas Adicionales**:
  - Material Design 3
  - Lifecycle ViewModel Compose
  - Coil (carga de imágenes)

## Estructura del Proyecto
```
app/src/main/java/com/example/gamezone/
├── data/
│   ├── FakeDatabase.kt          # Base de datos en memoria
│   └── ProductRepository.kt      # Repositorio de productos
├── models/
│   ├── Product.kt               # Modelo de producto
│   └── Users.kt                 # Modelo de usuario
├── viewModel/
│   ├── LoginViewModel.kt        # Lógica de login
│   ├── RegisterViewModel.kt     # Lógica de registro
│   └── ProductViewModel.kt      # Lógica de productos
├── views/
│   ├── InicioScreen.kt          # Pantalla inicial con logo animado
│   ├── LoginScreen.kt           # Pantalla de inicio de sesión ✨ MEJORADA
│   ├── RegisterScreen.kt        # Pantalla de registro ✨ MEJORADA
│   ├── HomeScreen.kt            # Pantalla principal
│   ├── CartScreen.kt            # Carrito de compras
│   └── ProductCard.kt           # Componente de tarjeta de producto
├── navigation/
│   └── AppNavigation.kt         # Navegación de la app
├── ui/theme/
│   ├── Color.kt                 # Paleta de colores
│   ├── Theme.kt                 # Tema de la app
│   └── Type.kt                  # Tipografía
└── MainActivity.kt              # Punto de entrada de la app
```

## Características Principales

### Sistema de Autenticación
- **Registro de usuarios** con validación de correo @duoc.cl
- **Inicio de sesión** seguro
- Validación de campos en tiempo real
- Gestión de usuarios en memoria (FakeDatabase)

### Catálogo de Juegos
- Exploración de productos
- Imágenes de videojuegos populares (The Last of Us, Zelda, God of War, etc.)
- Sistema de carrito de compras

### Pantalla de Inicio
- Logo de GameZone animado
- Navegación a Login/Registro
- Tema claro/oscuro alternante al tocar

## 🎨 Mejoras Implementadas (Noviembre 2025)

### LoginScreen.kt - Mejoras
✅ **Logo de GameZone** integrado en la parte superior
✅ **Diseño moderno** con Material Design 3
✅ **Iconos visuales** para email y contraseña
✅ **Toggle de visibilidad** para mostrar/ocultar contraseña
✅ **Indicador de carga** mientras se procesa el login
✅ **Validación visual** - botón deshabilitado si faltan datos
✅ **Bordes redondeados** y mejor espaciado
✅ **TopAppBar** con navegación mejorada
✅ **Texto de bienvenida** más amigable

### RegisterScreen.kt - Mejoras
✅ **Logo de GameZone** integrado
✅ **Campo de confirmación** de contraseña
✅ **Validación en tiempo real** de contraseñas coincidentes
✅ **Iconos para todos los campos** (persona, email, contraseña)
✅ **Toggle de visibilidad** para ambas contraseñas
✅ **Validación de longitud** mínima de contraseña (6 caracteres)
✅ **Mensajes de ayuda** bajo cada campo
✅ **Scroll vertical** para pantallas pequeñas
✅ **Indicador de carga** durante el registro
✅ **Validación visual** con colores de error
✅ **TopAppBar** consistente con el login

### Mejoras de UX/UI
- Campos de formulario con bordes redondeados (12dp)
- Colores del tema Material Design 3
- Feedback visual inmediato
- Botones deshabilitados cuando los datos son inválidos
- Textos de ayuda descriptivos
- Animaciones suaves en los iconos de contraseña

## Validaciones Implementadas

### Login
- ✅ Campos no pueden estar vacíos
- ✅ Verificación de credenciales contra la base de datos
- ✅ Mensajes de error claros

### Registro
- ✅ Todos los campos obligatorios
- ✅ Email debe terminar en @duoc.cl
- ✅ Contraseña mínimo 6 caracteres
- ✅ Las contraseñas deben coincidir
- ✅ El correo no debe estar registrado previamente
- ✅ Validación visual en tiempo real

## Limitaciones en Entorno Replit
**IMPORTANTE**: Esta aplicación Android NO puede ejecutarse en Replit porque:
1. Las apps Android requieren Android Runtime (ART) o un emulador
2. El entorno Linux de Replit no soporta emuladores Android
3. La aplicación está diseñada específicamente para dispositivos móviles

## Cómo Ejecutar Esta Aplicación

### Opción 1: Android Studio (Recomendado)
1. Descarga e instala [Android Studio](https://developer.android.com/studio)
2. Abre el proyecto en Android Studio
3. Configura un emulador Android o conecta un dispositivo físico
4. Click en "Run" (▶️) o presiona Shift+F10
5. Selecciona el dispositivo/emulador

### Opción 2: Línea de Comandos (Gradle)
```bash
# Compilar el proyecto
./gradlew build

# Generar APK debug
./gradlew assembleDebug

# El APK estará en: app/build/outputs/apk/debug/app-debug.apk
# Instalar en dispositivo conectado via ADB
adb install app/build/outputs/apk/debug/app-debug.apk
```

## Uso en Replit
En Replit puedes:
- ✅ Ver y editar el código fuente
- ✅ Explorar la arquitectura del proyecto
- ✅ Modificar las pantallas y componentes
- ✅ Revisar la lógica de negocio
- ❌ NO ejecutar la aplicación (requiere Android)

## Requisitos del Sistema (para desarrollo local)
- Android Studio Arctic Fox o superior
- JDK 11
- Android SDK API 24-34
- Gradle 8.13.0
- 4GB RAM mínimo (8GB recomendado)

## Recursos de la Aplicación
La app incluye imágenes de juegos populares:
- The Last of Us 1 y 2
- God of War
- Zelda
- Cyberpunk
- Forza
- Black Ops 3
- Odyssey

## Próximas Mejoras Sugeridas
- Implementar base de datos persistente (Room o SQLite)
- Agregar autenticación con Firebase
- Implementar sistema de pagos
- Añadir filtros y búsqueda de productos
- Implementar perfil de usuario
- Agregar wishlist de productos
- Sistema de calificaciones y reseñas

## Fecha de Actualizaciones
- **Proyecto importado**: 02 de Noviembre, 2025
- **Mejoras UI/UX Login y Registro**: 02 de Noviembre, 2025
