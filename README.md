# Voice to Text Messenger

Una aplicación móvil moderna desarrollada con React Native y Expo que permite grabar notas de voz, convertirlas a texto y enviarlas directamente a WhatsApp o Telegram.

## 🚀 Características

- **Grabación de voz de alta calidad** - Graba notas de voz con audio cristalino
- **Conversión voz a texto** - Transcripción automática de audio a texto
- **Integración con mensajería** - Envía transcripciones directamente a WhatsApp y Telegram
- **Historial completo** - Guarda y gestiona todas tus grabaciones
- **Reproducción de texto** - Escucha las transcripciones con síntesis de voz
- **Configuración personalizable** - Ajusta idioma, velocidad de reproducción y más
- **Interfaz moderna** - Diseño elegante y fácil de usar
- **Multiplataforma** - Compatible con iOS, Android y Web

## 📱 Capturas de pantalla

La aplicación cuenta con tres pantallas principales:

1. **Grabación** - Interfaz principal para grabar y transcribir audio
2. **Historial** - Visualiza y gestiona todas tus grabaciones anteriores
3. **Configuración** - Personaliza la experiencia de la aplicación

## 🛠️ Tecnologías utilizadas

- **React Native** - Framework de desarrollo móvil
- **Expo SDK 52** - Plataforma de desarrollo y herramientas
- **Expo Router 4** - Navegación basada en archivos
- **TypeScript** - Tipado estático para JavaScript
- **Expo AV** - Grabación y reproducción de audio
- **Expo Speech** - Síntesis de voz
- **AsyncStorage** - Almacenamiento local persistente
- **Expo Vector Icons** - Iconografía moderna

## 📋 Requisitos previos

- Node.js (versión 18 o superior)
- npm o yarn
- Expo CLI
- Dispositivo móvil o emulador para pruebas

## 🚀 Instalación y configuración

1. **Clona el repositorio**
   ```bash
   git clone https://github.com/tu-usuario/voice-to-text-messenger.git
   cd voice-to-text-messenger
   ```

2. **Instala las dependencias**
   ```bash
   npm install
   ```

3. **Inicia el servidor de desarrollo**
   ```bash
   npm start
   ```

4. **Ejecuta en tu dispositivo**
   - Escanea el código QR con la app Expo Go
   - O ejecuta en emulador: `npm run android` o `npm run ios`

## 📁 Estructura del proyecto

```
voice-to-text-messenger/
├── app/                          # Rutas de la aplicación (Expo Router)
│   ├── _layout.tsx              # Layout raíz
│   └── (tabs)/                  # Navegación por pestañas
│       ├── _layout.tsx          # Configuración de pestañas
│       ├── index.tsx            # Pantalla de grabación
│       ├── history.tsx          # Historial de grabaciones
│       └── settings.tsx         # Configuración
├── components/                   # Componentes reutilizables
│   ├── ActionButton.tsx         # Botones de acción
│   ├── RecordingIndicator.tsx   # Indicador de grabación
│   └── TranscriptionCard.tsx    # Tarjeta de transcripción
├── hooks/                       # Hooks personalizados
│   ├── useFrameworkReady.ts     # Hook de inicialización
│   ├── useSpeechRecognition.ts  # Hook para reconocimiento de voz
│   └── useVoiceRecording.ts     # Hook para grabación de voz
├── assets/                      # Recursos estáticos
│   ├── icon.png                 # Icono de la app
│   ├── splash.png               # Pantalla de carga
│   └── adaptive-icon.png        # Icono adaptativo Android
├── app.json                     # Configuración de Expo
├── package.json                 # Dependencias del proyecto
└── tsconfig.json               # Configuración de TypeScript
```

## 🎯 Funcionalidades principales

### Grabación de voz
- Toca el botón del micrófono para iniciar la grabación
- Visualiza el tiempo de grabación en tiempo real
- Detén la grabación tocando el botón de parar

### Transcripción automática
- El audio se procesa automáticamente después de la grabación
- La transcripción aparece en una tarjeta elegante
- Opción de reproducir el texto convertido a voz

### Envío a aplicaciones de mensajería
- **WhatsApp**: Envía la transcripción directamente a WhatsApp
- **Telegram**: Comparte el texto en Telegram
- Detección automática de aplicaciones instaladas

### Gestión del historial
- Todas las grabaciones se guardan automáticamente
- Visualiza fecha, duración y transcripción
- Elimina grabaciones individuales o limpia todo el historial
- Reproduce transcripciones desde el historial

### Configuración personalizable
- **Idioma**: Español e Inglés para reconocimiento de voz
- **Velocidad de reproducción**: 0.5x, 1.0x, 1.5x, 2.0x
- **Guardado automático**: Activa/desactiva el guardado automático
- **Notificaciones**: Controla las notificaciones de la app
- **Modo oscuro**: Próximamente disponible

## 🔧 Configuración avanzada

### Permisos requeridos

La aplicación requiere los siguientes permisos:

- **Micrófono**: Para grabar audio
- **Almacenamiento**: Para guardar grabaciones (Android)

### Variables de entorno

Crea un archivo `.env` en la raíz del proyecto para configuraciones personalizadas:

```env
EXPO_PUBLIC_API_URL=https://tu-api.com
EXPO_PUBLIC_SPEECH_API_KEY=tu-clave-api
```

### Personalización de la transcripción

Actualmente la app usa transcripciones simuladas para demostración. Para implementar transcripción real:

1. **Google Speech-to-Text API**
2. **Azure Speech Services**
3. **AWS Transcribe**
4. **OpenAI Whisper API**

Modifica el archivo `hooks/useSpeechRecognition.ts` para integrar tu servicio preferido.

## 📱 Compatibilidad de plataformas

| Característica | iOS | Android | Web |
|----------------|-----|---------|-----|
| Grabación de voz | ✅ | ✅ | ✅* |
| Transcripción | ✅ | ✅ | ✅ |
| WhatsApp | ✅ | ✅ | ❌ |
| Telegram | ✅ | ✅ | ❌ |
| Síntesis de voz | ✅ | ✅ | ✅ |
| Almacenamiento | ✅ | ✅ | ✅ |

*La grabación web requiere HTTPS en producción

## 🚀 Despliegue

### Expo Application Services (EAS)

1. **Instala EAS CLI**
   ```bash
   npm install -g eas-cli
   ```

2. **Configura el proyecto**
   ```bash
   eas build:configure
   ```

3. **Construye para producción**
   ```bash
   eas build --platform all
   ```

4. **Publica en las tiendas**
   ```bash
   eas submit --platform all
   ```

### Web (Netlify/Vercel)

```bash
npm run build:web
```

Sube la carpeta `dist` a tu proveedor de hosting preferido.

## 🤝 Contribución

Las contribuciones son bienvenidas. Para contribuir:

1. Fork el proyecto
2. Crea una rama para tu característica (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📝 Roadmap

- [ ] Transcripción real con APIs de terceros
- [ ] Modo oscuro completo
- [ ] Soporte para más idiomas
- [ ] Exportación de transcripciones
- [ ] Sincronización en la nube
- [ ] Reconocimiento de voz offline
- [ ] Edición de transcripciones
- [ ] Etiquetas y categorías
- [ ] Búsqueda en el historial
- [ ] Compartir en más aplicaciones

## 🐛 Problemas conocidos

- La transcripción actual es simulada (requiere integración con API real)
- El envío a WhatsApp/Telegram no funciona en web
- Algunas características nativas no están disponibles en web

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 👥 Autores

- **Tu Nombre** - *Desarrollo inicial* - [tu-github](https://github.com/tu-usuario)

## 🙏 Agradecimientos

- Expo team por las excelentes herramientas de desarrollo
- React Native community por los recursos y documentación
- Iconos proporcionados por Expo Vector Icons
- Inspiración de diseño de aplicaciones modernas de productividad

## 📞 Soporte

Si tienes preguntas o necesitas ayuda:

- 📧 Email: tu-email@ejemplo.com
- 🐛 Issues: [GitHub Issues](https://github.com/tu-usuario/voice-to-text-messenger/issues)
- 💬 Discusiones: [GitHub Discussions](https://github.com/tu-usuario/voice-to-text-messenger/discussions)

---

⭐ Si este proyecto te ha sido útil, ¡no olvides darle una estrella en GitHub!
