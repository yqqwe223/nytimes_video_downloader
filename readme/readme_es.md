# 🗽 Analizador de Videos de NYTimes

> Una herramienta ligera, rápida y versátil para extraer contenido de video de The New York Times (Versión educativa y de investigación)

[🌐 Demostración en línea](https://twittervideodownloaderx.com/nytimes_downloader_sp) • [📝 Guía de uso](#-guía-de-uso) • [❓ Preguntas frecuentes](#-preguntas-frecuentes)

---

## 📋 Descripción del proyecto

Este proyecto es una herramienta de análisis de video basada en web, diseñada para extraer de forma segura metadatos de recursos multimedia de artículos públicamente accesibles en el sitio web de The New York Times, ofreciendo opciones de conversión de formato y guardado local. No requiere instalación de software cliente ni registro de cuenta: úsala directamente desde tu navegador.

> ⚠️ **Aviso importante**: Esta herramienta está diseñada exclusivamente para aprendizaje personal, investigación técnica y uso dentro de límites razonables. Por favor, cumple con los [Términos de Servicio de NYTimes](https://www.nytimes.com/content/help/rights/sale/terms-of-service.html), la 《Ley de Derechos de Autor de EE.UU.》 y otras regulaciones aplicables. Respeta el trabajo de las organizaciones de noticias y los creadores; no utilices el contenido descargado con fines comerciales ni para infringir los derechos de terceros. **Esta herramienta solo admite contenido de video accesible públicamente y no elude muros de pago, restricciones de suscripción ni contenido que requiera inicio de sesión.**

---

## ✨ Funciones principales

- 🔗 **Análisis de enlaces**: Compatible con URLs estándar de artículos/páginas de video de NYTimes; detección automática de recursos de video disponibles públicamente
- 📥 **Exportación multi-formato**:
  - Flujos de video públicos (admite opciones de resolución públicas proporcionadas por la plataforma)
  - Extracción de audio → Formato MP3 (conveniente para escuchar informes de noticias/pódcasts sin conexión)
  - Clip de video → Conversión a GIF animado (ideal para crear materiales educativos/resúmenes de contenido)
- 🌍 **Interfaz multilingüe**: Soporte para español, inglés, chino, japonés, coreano y más idiomas
- 📱 **Compatibilidad multiplataforma**: Funciona perfectamente en Chrome / Firefox / Safari / Edge; experiencia optimizada para dispositivos móviles y tablets
- 🔒 **Privacidad priorizada**: No requiere inicio de sesión en cuenta de NYTimes, sin recopilación de datos personales; proceso de análisis completamente anónimo
- ⚡ **Procesamiento rápido**: El análisis se completa en un promedio de 5-10 segundos; admite solicitudes simultáneas

---

## 🚀 Inicio rápido

### Uso en línea (recomendado)
1. Accede a [https://twittervideodownloaderx.com/nytimes_downloader_sp](https://twittervideodownloaderx.com/nytimes_downloader_sp)
2. Copia el enlace de la página de video objetivo (ejemplo: `https://www.nytimes.com//01/01/world/example-video.html`)
3. Pega el enlace en el campo de entrada → Haz clic en el botón 「Analizar」
4. Selecciona el formato deseado → Guarda el archivo siguiendo las indicaciones del navegador

### Implementación local (para desarrolladores)
```bash
# Clonar el repositorio
git clone https://github.com/your-repo/nytimes-video-parser.git

# Instalar dependencias
cd nytimes-video-parser && npm install

# Configurar variables de entorno (opcional)
cp .env.example .env

# Iniciar servidor de desarrollo
npm run dev
```

> 💡 Nota: Este proyecto utiliza una arquitectura basada en Node.js + Express. Consulta la documentación detallada de implementación en `/docs/DEPLOY.md`

---

## 🛠 Stack tecnológico

| Módulo | Tecnologías utilizadas |
|--------|------------------------|
| Frontend | Vue 3 + TypeScript + Vite |
| Backend | Node.js + Express + Axios |
| Procesamiento de video | ffmpeg.wasm (conversión ligera en el lado del cliente) |
| Proxy de reenvío | Cloudflare Workers / Middleware personalizado |
| Internacionalización | vue-i18n + Paquetes de idioma JSON |

---

## 📚 Guía de uso

### Flujo de operación básico
```
1. Obtener el enlace del video
   └─ Abre el artículo/página de video objetivo en NYTimes → Copia la URL desde la barra de direcciones del navegador

2. Enviar solicitud de análisis
   └─ Pega el enlace en el campo de entrada de la herramienta → Haz clic en 「Iniciar análisis」

3. Seleccionar configuración de salida
   ├─ 🎬 Descargar video: Elegir resolución disponible (solo contenido público)
   ├─ 🎵 Extraer audio: Generar archivo MP3 (ideal para escuchar noticias/pódcasts sin conexión)
   └─ 🎞 Generar GIF: Crear animación desde un rango de tiempo especificado (recomendado: ≤15 segundos)

4. Guardar el archivo
   └─ El recurso se abrirá en una nueva pestaña → Clic derecho/menú → 「Guardar como」
```

### Consejos para uso en dispositivos móviles
- iOS Safari: Botón Compartir → 「Guardar en Archivos」
- Android Chrome: Mantener presionada la vista previa del video → 「Descargar video」
- Si el video se reproduce automáticamente: Haz clic en `⋮` en la esquina superior derecha del reproductor → Selecciona 「Descargar」

---

## ❓ Preguntas frecuentes

**P: ¿Dónde se guardan los archivos descargados?**  
R: Los archivos se guardan en la carpeta de descargas configurada en tu navegador. Puedes verificar o modificar esta ruta en la configuración del navegador.

**P: ¿Puedo analizar contenido con muro de pago, exclusivo para suscriptores o que requiere inicio de sesión?**  
R: No. Esta herramienta solo funciona con contenido de video accesible públicamente y respeta los permisos de acceso del contenido original. El contenido detrás de muros de pago, restricciones de suscripción o que requiere inicio de sesión no es compatible.

**P: ¿Se reduce la calidad de imagen/audio después de la conversión?**  
R: Las descargas de video mantienen la tasa de bits original de la resolución seleccionada. El formato MP3 utiliza codificación estándar de 128 kbps. El formato GIF optimiza la tasa de fotogramas según la duración para equilibrar el tamaño del archivo y la fluidez.

**P: ¿Se almacena el historial de descargas o la caché?**  
R: No. Todos los recursos se transmiten directamente al dispositivo del usuario a través de un proxy temporal; el servidor no almacena ninguna solicitud ni archivo multimedia.

**P: ¿Qué debo hacer si falla el análisis?**  
R: Por favor, verifica: ① Que el enlace apunte a una página de video pública válida ② Que tu conexión a internet sea estable ③ Intenta usar otro navegador. Si el problema persiste, no dudes en reportarlo mediante un Issue.

---

## ⚖️ Cumplimiento normativo y Descargo de responsabilidad

- Esta herramienta **no elude ni viola ninguna medida de protección técnica, muro de pago o control de acceso** de la plataforma; únicamente obtiene metadatos a través de interfaces disponibles públicamente
- El usuario es responsable de verificar que su uso cumpla con la legislación local y los términos de servicio de la plataforma
- Casos de uso recomendados: Archivos de aprendizaje personal, referencia para investigación de noticias, preparación de materiales educativos... siempre dentro del marco del uso justo (Fair Use)
- Si descubres contenido que pueda infringir derechos o tienes preguntas sobre derechos de autor, por favor contacta al canal oficial a través de la [Página de Contacto de Derechos de Autor de NYTimes](https://www.nytimes.com/content/help/rights/copyright/copyright-contact.html)
- Esta herramienta no está afiliada, respaldada ni autorizada por The New York Times Company. Todas las marcas comerciales y derechos de autor del contenido pertenecen a sus respectivos propietarios

---

## 🤝 Guía de contribución

¡Agradecemos tus Pull Requests y reportes de Issues! Antes de contribuir, por favor revisa:
- [Estándares de código](/CONTRIBUTING.md)
- [Guía de traducción multilingüe](/locales/README.md)
- [Requisitos de seguridad y cumplimiento](/SECURITY.md)

---

## 📄 Licencia

Este proyecto se publica bajo la [Licencia MIT](/LICENSE). Puede utilizarse gratuitamente con fines educativos y de investigación. Para uso comercial, por favor verifica cuidadosamente el cumplimiento de las normativas legales aplicables.

---

> 🌟 Si esta herramienta te ha sido útil, ¡por favor ✨dale una Estrella (Star)! Tu apoyo es la mayor motivación para que sigamos manteniendo y mejorando este proyecto~

*Última actualización: Mayo  | Versión: v1.0.0*