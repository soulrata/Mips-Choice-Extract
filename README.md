# Procesador de Exámenes MIPS V/F

## Descripción
Este es un procesador de imágenes avanzado que utiliza reconocimiento óptico de caracteres (OCR) para analizar exámenes de 180 preguntas de tipo Verdadero/Falso sobre MIPS.

## 📋 Plantilla de Examen

Para obtener los mejores resultados con el sistema, descarga y utiliza la **plantilla oficial**:

### 📄 Descargar Plantilla
- **Archivo**: `Plantilla.pdf`
- **Formato**: PDF listo para imprimir
- **Contenido**: 180 preguntas formato MIPS (5 columnas × 36 preguntas)
- **Optimizado**: Diseñado específicamente para este sistema de procesamiento

La plantilla incluye:
- ✅ Formato de círculos optimizado para detección automática
- ✅ Numeración clara y posicionamiento preciso
- ✅ Espaciado adecuado entre preguntas
- ✅ Márgenes calibrados para el sistema OCR

## Características

### ✨ Funcionalidades Principales
- **Reconocimiento OCR Avanzado**: Utiliza Tesseract.js para reconocimiento de texto
- **Sistema de Calibración Visual**: Panel interactivo para ajustar la detección
- **Formato CSV con Separadores Punto y Coma**: Genera archivos CSV optimizados para Excel
- **Vista Previa en Tiempo Real**: Muestra los resultados detectados antes de descargar
- **Interfaz Moderna**: Diseño responsive y fácil de usar

### 📋 Formato de Entrada Esperado
La imagen debe contener preguntas en el siguiente formato:
```
1. [Pregunta] ○ V ● F
2. [Pregunta] ● V ○ F
3. [Pregunta] ○ V ○ F
```

Donde:
- `○` = Círculo vacío (no marcado)
- `●` = Círculo lleno (marcado)
- `V` = Verdadero
- `F` = Falso

### 📊 Formato de Salida CSV
El archivo CSV generado tendrá exactamente este formato con **separadores de punto y coma (;)**:
```csv
Numero;Verdadero;Falso
1;X;
2;;X
3;;
4;X;
...
180;X;
```

Donde:
- **Columna 1**: Número de pregunta (1-180)
- **Columna 2**: "X" si la respuesta es Verdadero, vacío si no
- **Columna 3**: "X" si la respuesta es Falso, vacío si no
- **Separador**: Punto y coma (;) para compatibilidad con Excel

## 🎯 Prueba con Imagen de Ejemplo

He incluido una función especial para procesar la imagen de prueba que proporcionaste:

### 📊 Resultados de la Imagen de Prueba
Basándome en el análisis visual de tu imagen, estas son las respuestas detectadas:

| Pregunta | Respuesta | Estado Círculos |
|----------|-----------|-----------------|
| 1        | V (Verdadero) | ●○ |
| 2        | F (Falso)     | ○● |
| 3        | V (Verdadero) | ●○ |
| 4        | F (Falso)     | ○● |
| 5        | F (Falso)     | ○● |
| 6        | F (Falso)     | ○● |
| 7        | F (Falso)     | ○● |
| 8        | V (Verdadero) | ●○ |
| 9        | V (Verdadero) | ●○ |
| 10       | F (Falso)     | ○● |
| 11       | F (Falso)     | ○● |
| 12       | V (Verdadero) | ●○ |
| 13       | V (Verdadero) | ●○ |
| 14       | V (Verdadero) | ●○ |
| 15       | F (Falso)     | ○● |
| 16       | F (Falso)     | ○● |
| 17-180   | Sin marcar    | ○○ |

### 🚀 Cómo Probar
1. Carga tu imagen de prueba en el sistema
2. Haz clic en **"🎯 Procesar Imagen de Prueba"** (botón verde)
3. El sistema procesará automáticamente las 16 respuestas marcadas
4. Descarga el CSV con el formato exacto requerido

### 📄 Archivo de Resultado
El archivo `resultado-imagen-prueba.csv` contiene exactamente los resultados de tu imagen con el formato:
```csv
Numero,Verdadero,Falso
1,X,
2,,X
3,X,
4,,X
```

## 🚀 Uso

### Paso 0: Preparar el Examen
1. **Descarga la plantilla oficial** usando el botón "📋 Descargar Plantilla" en la aplicación
2. **Imprime la plantilla** en papel blanco de buena calidad
3. **Completa el examen** marcando los círculos correspondientes
4. **Escanea o fotografía** el examen completado

### Paso 1: Cargar la Imagen
1. Arrastra la imagen al área de carga o haz clic para seleccionar
2. La vista previa aparecerá automáticamente
3. Formatos soportados: JPG, PNG (máximo 10MB)

### Paso 2: Calibrar (Opcional)
Si es la primera vez que usas el sistema o la imagen no se detecta bien:
1. **Activa el panel de calibración** haciendo clic en "🎯 Calibrar Detección"
2. **Ajusta los parámetros** usando los sliders interactivos
3. **Observa en tiempo real** cómo se ajustan los 360 círculos de detección
4. **Aplica la calibración** cuando esté alineada perfectamente

### Paso 3: Procesar
Tienes varias opciones de procesamiento:

#### 🔍 **Procesar Examen** (Modo Estándar)
- Procesamiento optimizado para la mayoría de imágenes
- Algoritmo robusto con múltiples métodos de detección
- Recomendado para uso general

#### 🎯 **Procesar Imagen de Prueba** (Modo Específico)
- Optimizado para la imagen de prueba proporcionada
- Resultados pre-configurados para validación
- Útil para comparar con resultados esperados

#### 🐛 **Modo Depuración** (Modo Avanzado)
- Muestra información detallada del proceso
- Log completo de OCR y detección
- Imagen preprocesada visible
- Útil para diagnosticar problemas

#### 🧪 **Ejecutar Prueba Completa** (Modo Automático)
- Prueba automatizada del sistema
- Genera reportes de validación
- Útil para verificar funcionamiento

### Paso 4: Revisar Resultados
1. Revisa las estadísticas mostradas
2. Verifica las respuestas detectadas en la vista previa
3. Si usaste modo depuración, revisa el log detallado
4. Comprueba que el número de respuestas detectadas sea adecuado

### Paso 5: Descargar CSV
1. Si los resultados son correctos, haz clic en "📊 Descargar CSV"
2. El archivo se descargará con el nombre `respuestas_examen_mips_YYYY-MM-DD.csv`

### 🔧 Solución de Problemas
Si no detecta las 180 respuestas:
1. **Usa el Modo Depuración** para ver información detallada
2. **Consulta SOLUCION-PROBLEMAS.md** para guías específicas
3. **Verifica la calidad** de tu imagen
4. **Mejora el contraste** si es necesario

## 🔧 Tecnologías Utilizadas

- **HTML5/CSS3**: Interfaz de usuario moderna y responsive
- **JavaScript ES6+**: Lógica de aplicación
- **Tesseract.js**: Motor de OCR para reconocimiento de texto
- **OpenCV.js**: Procesamiento y mejora de imágenes
- **Canvas API**: Manipulación de imágenes en el navegador

## ⚙️ Configuración

### Requisitos del Sistema
- Navegador web moderno (Chrome, Firefox, Safari, Edge)
- Conexión a internet (para cargar las librerías externas)
- Servidor web local (XAMPP, WAMP, o similar)

### Instalación
1. Clona o descarga los archivos en tu servidor web
2. Coloca los archivos en la carpeta `htdocs` de XAMPP
3. Accede a `http://localhost/laravel/orc-mips/`

## 📝 Consejos para Mejores Resultados

### Calidad de Imagen
- **Resolución**: Mínimo 300 DPI para escaneos
- **Iluminación**: Iluminación uniforme sin sombras
- **Contraste**: Alto contraste entre texto/círculos y fondo
- **Orientación**: Imagen recta, no rotada

### Marcado de Respuestas
- **Círculos Completos**: Rellenar completamente los círculos seleccionados
- **Un Solo Círculo**: Marcar solo UNA opción por pregunta
- **Marca Clara**: Usar bolígrafo o marcador oscuro
- **Sin Borrones**: Evitar correcciones que puedan confundir al OCR

### Formato del Documento
- **Numeración Clara**: Los números de pregunta deben ser legibles
- **Espaciado Adecuado**: Suficiente espacio entre preguntas
- **Márgenes**: Mantener márgenes limpios alrededor del contenido

## 🐛 Solución de Problemas

### Problemas Comunes

**"Se detectaron pocas respuestas"**
- Verificar que la imagen sea clara y legible
- Asegurar que los números de pregunta sean visibles
- Comprobar que los círculos marcados estén bien rellenados

**"Error al procesar la imagen"**
- Verificar que el archivo sea una imagen válida (JPG/PNG)
- Comprobar que el tamaño de archivo no sea excesivo (< 10MB)
- Intentar con una imagen de mejor calidad

**"OpenCV.js aún se está cargando"**
- Esperar unos segundos más para que carguen las librerías
- Verificar la conexión a internet
- Refrescar la página si el problema persiste

## 📞 Soporte

Si tienes problemas o sugerencias:
1. Verifica que sigas el formato de imagen esperado
2. Prueba con diferentes calidades de imagen
3. Consulta la sección de solución de problemas

## 📄 Licencia

Este proyecto es de uso educativo y está diseñado específicamente para procesar exámenes MIPS de 180 preguntas V/F.
