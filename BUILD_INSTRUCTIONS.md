# 📱 Guía para Crear APK de Android

Esta guía te explica cómo crear un APK de tu aplicación Voice to Text Messenger para instalar directamente en dispositivos Android.

## 🚀 Opciones de Build

### Opción 1: EAS Build (Recomendado)

EAS Build es el servicio oficial de Expo para crear builds de producción.

#### Paso 1: Instalar EAS CLI
```bash
npm install -g eas-cli
```

#### Paso 2: Iniciar sesión en Expo
```bash
eas login
```

#### Paso 3: Configurar el proyecto
```bash
eas build:configure
```

#### Paso 4: Crear APK de prueba
```bash
eas build -p android --profile preview
```

#### Paso 5: Crear APK de producción
```bash
eas build -p android --profile production
```

### Opción 2: Expo Development Build

Para desarrollo y pruebas rápidas:

```bash
eas build --profile development --platform android
```

### Opción 3: Build Local (Avanzado)

Si prefieres hacer el build localmente:

```bash
eas build --local -p android --profile preview
```

## 📋 Configuración Previa

### 1. Actualizar app.json

Asegúrate de que tu `app.json` tenga:
- `android.package`: Identificador único de tu app
- `ios.bundleIdentifier`: Para builds de iOS
- Permisos necesarios en `android.permissions`

### 2. Crear cuenta en Expo

1. Ve a [expo.dev](https://expo.dev)
2. Crea una cuenta gratuita
3. Crea un nuevo proyecto

### 3. Obtener Project ID

```bash
eas project:info
```

Copia el Project ID y actualízalo en `app.json` en `extra.eas.projectId`.

## 🔧 Tipos de Build

### Preview Build (APK)
- **Propósito**: Pruebas internas
- **Formato**: APK
- **Instalación**: Directa en dispositivo
- **Comando**: `eas build -p android --profile preview`

### Production Build (AAB)
- **Propósito**: Google Play Store
- **Formato**: Android App Bundle (AAB)
- **Instalación**: A través de Play Store
- **Comando**: `eas build -p android --profile production`

### Development Build
- **Propósito**: Desarrollo con Expo Dev Client
- **Formato**: APK con desarrollo habilitado
- **Instalación**: Directa en dispositivo
- **Comando**: `eas build -p android --profile development`

## 📱 Instalación del APK

### Método 1: Descarga directa
1. Una vez completado el build, recibirás un enlace
2. Abre el enlace en tu dispositivo Android
3. Descarga el APK
4. Habilita "Instalar desde fuentes desconocidas" en Configuración
5. Instala el APK

### Método 2: ADB (Android Debug Bridge)
```bash
adb install ruta/al/archivo.apk
```

### Método 3: Compartir enlace
- Comparte el enlace de descarga con otros usuarios
- El enlace es válido por 30 días

## ⚙️ Configuración de Permisos

Para que la app funcione correctamente, necesita estos permisos:

```json
"permissions": [
  "android.permission.RECORD_AUDIO",
  "android.permission.WRITE_EXTERNAL_STORAGE",
  "android.permission.READ_EXTERNAL_STORAGE"
]
```

## 🐛 Solución de Problemas

### Error: "No project ID"
```bash
eas project:init
```

### Error: "Build failed"
1. Verifica que todos los archivos estén commitados en git
2. Revisa los logs del build
3. Asegúrate de que las dependencias estén actualizadas

### Error: "Invalid package name"
- El package name debe ser único
- Formato: `com.tucompania.nombreapp`
- Solo letras, números y puntos

### APK no instala
1. Habilita "Fuentes desconocidas" en Configuración
2. Verifica que el dispositivo tenga espacio suficiente
3. Intenta reiniciar el dispositivo

## 📊 Monitoreo del Build

### Ver estado del build
```bash
eas build:list
```

### Ver logs detallados
```bash
eas build:view [BUILD_ID]
```

### Cancelar build
```bash
eas build:cancel [BUILD_ID]
```

## 🔒 Firma de la Aplicación

EAS Build maneja automáticamente la firma de la aplicación:

- **Desarrollo**: Firma automática
- **Producción**: Genera keystore automáticamente
- **Custom**: Puedes subir tu propio keystore

## 💡 Consejos Adicionales

### 1. Optimización del tamaño
- Usa `--clear-cache` si el APK es muy grande
- Revisa las dependencias innecesarias

### 2. Testing
- Prueba el APK en diferentes dispositivos
- Verifica todos los permisos y funcionalidades

### 3. Distribución
- Para distribución interna, usa el perfil `preview`
- Para Play Store, usa el perfil `production`

### 4. Versionado
- Incrementa la versión en `app.json` para cada build
- Usa semantic versioning (1.0.0, 1.0.1, etc.)

## 📞 Soporte

Si tienes problemas:

1. **Documentación oficial**: [docs.expo.dev](https://docs.expo.dev)
2. **Discord de Expo**: Comunidad activa
3. **GitHub Issues**: Para bugs específicos
4. **Stack Overflow**: Para preguntas técnicas

## 🎯 Comandos Rápidos

```bash
# Build APK de prueba
eas build -p android --profile preview

# Build para producción
eas build -p android --profile production

# Ver builds anteriores
eas build:list

# Configurar proyecto
eas build:configure

# Información del proyecto
eas project:info
```

---

¡Con esta configuración podrás crear APKs de tu aplicación Voice to Text Messenger y distribuirlos fácilmente!