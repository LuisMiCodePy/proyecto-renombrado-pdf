# 📄 Automatización de Extracción y Renombrado de PDFs (Licencias)

Este proyecto utiliza Python y la API de Google Cloud Vision para automatizar el procesamiento de documentos PDF (licencias de conducir). Realiza dos tareas principales:
1. **Renombrado Masivo**: Identifica el folio de 8 dígitos y renombra el archivo como `Licencia_XXXXXXXX.pdf`.
2. **Extracción de Datos**: Genera una base de datos en CSV con información clave como Nombre, CURP, Sexo, Vigencia y Tipo de Trámite.

## 🚀 Funcionalidades
- **OCR de Alta Precisión**: Uso de Google Cloud Vision para lectura de texto en imágenes de 400 DPI.
- **Lógica de Seguridad**: Filtros mediante expresiones regulares (`regex`) para asegurar que solo se extraigan folios válidos de 8 dígitos.
- **Búsqueda por Coordenadas**: Localización precisa de datos específicos (Nombre, Trámite) basada en etiquetas en el documento.
- **Manejo de Duplicados**: Sistema automático para evitar la sobreescritura de archivos durante el renombrado.

## 🛠️ Requisitos Previos

### 1. Dependencias del Sistema
Es necesario instalar **Poppler** para la conversión de PDF a imágenes:
- **Windows**: Descarga el binario de Poppler y añade la ruta de `bin` al script o a tus variables de entorno.
- **Linux/Mac**: `sudo apt-get install poppler-utils` o `brew install poppler`.

### 2. Google Cloud Vision
- Debes tener una cuenta en Google Cloud Console.
- Habilita la **Cloud Vision API**.
- Crea una **Cuenta de Servicio**, descarga la llave en formato `.json` y colócala en tu carpeta de descargas (o actualiza la ruta en el script).

### 3. Instalación de Librerías
```bash
pip install google-cloud-vision pdf2image pandas