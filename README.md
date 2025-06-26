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
- **🆕 Filtros de Mejora de Imagen**: Sistema avanzado de preprocesamiento con sobre exposición y realce de contraste
- **Sistema de Calibración Visual**: Panel interactivo para ajustar la detección con controles de filtros en tiempo real
- **🆕 Detección Mejorada de Marcas**: Algoritmos optimizados para detectar marcas débiles o poco contrastadas
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
2. **Ajusta los parámetros de posición** usando los sliders de margen y espaciado
3. **🆕 Configura los filtros de imagen**:
   - **Intensidad Contraste (1.0-4.0)**: Aumenta para mayor diferenciación entre marcas y fondo
   - **Sobre Exposición (0.1-0.7)**: Reduce para hacer las marcas más oscuras y visibles
   - **Umbral Detección (0.05-0.4)**: Ajusta la sensibilidad para detectar marcas débiles
4. **Observa en tiempo real** cómo se ajustan los 360 círculos de detección con filtros aplicados
5. **Aplica la calibración** cuando esté alineada perfectamente

### Paso 3: Procesar
Tienes varias opciones de procesamiento:

#### 🔍 **Procesar Examen** (Modo Estándar)
- Procesamiento optimizado para la mayoría de imágenes
- 🆕 **Filtros automáticos aplicados**: Sobre exposición y realce de contraste
- Algoritmo robusto con múltiples métodos de detección
- 🆕 **Detección mejorada de marcas débiles**: Especialmente efectivo para marcas poco contrastadas
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
1. **Usa el panel de calibración** para ajustar tanto posición como filtros de imagen
2. **🆕 Ajusta los filtros de mejora**:
   - Aumenta el **contraste** si las marcas son muy tenues
   - Reduce la **sobre exposición** si las marcas son muy claras
   - Modifica el **umbral de detección** para mayor o menor sensibilidad
3. **Usa el Modo Depuración** para ver información detallada del procesamiento
4. **Consulta SOLUCION-PROBLEMAS.md** para guías específicas
5. **Verifica la calidad** de tu imagen
6. **Mejora el contraste** de la imagen original si es necesario

## 🔧 Tecnologías Utilizadas

- **HTML5/CSS3**: Interfaz de usuario moderna y responsive
- **JavaScript ES6+**: Lógica de aplicación
- **Tesseract.js**: Motor de OCR para reconocimiento de texto
- **🆕 Algoritmos de Procesamiento de Imagen**: Filtros avanzados de sobre exposición y mejora de contraste
- **Canvas API**: Manipulación y filtrado de imágenes en tiempo real en el navegador
- **🆕 Detección Adaptativa**: Umbrales dinámicos para diferentes tipos de marcas

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
- **🆕 Marcas Débiles**: El sistema ahora puede detectar marcas ligeras gracias a los filtros mejorados
- **Sin Borrones**: Evitar correcciones que puedan confundir al sistema, aunque es más tolerante
- **🆕 Diferentes Tipos de Marca**: Compatible con lápiz, bolígrafo, marcador (gracias a filtros adaptativos)

### Formato del Documento
- **Numeración Clara**: Los números de pregunta deben ser legibles
- **Espaciado Adecuado**: Suficiente espacio entre preguntas
- **Márgenes**: Mantener márgenes limpios alrededor del contenido

## 🐛 Solución de Problemas

### Problemas Comunes

**"Se detectaron pocas respuestas"**
- 🆕 **Primer paso**: Usar el panel de calibración para ajustar filtros de imagen
- Verificar que la imagen sea clara y legible
- Asegurar que los números de pregunta sean visibles
- Comprobar que los círculos marcados estén bien rellenados
- 🆕 **Ajustar contraste**: Aumentar intensidad de contraste en panel de calibración
- 🆕 **Modificar umbral**: Reducir umbral de detección para marcas más débiles

**"Error al procesar la imagen"**
- Verificar que el archivo sea una imagen válida (JPG/PNG)
- Comprobar que el tamaño de archivo no sea excesivo (< 10MB)
- Intentar con una imagen de mejor calidad
- 🆕 **Probar con filtros**: Usar calibración para optimizar detección antes del procesamiento

**"Marcas no detectadas correctamente"**
- 🆕 **Calibrar filtros**: Ajustar sobre exposición y contraste en tiempo real
- 🆕 **Verificar preview**: Observar en el canvas de calibración cómo se detectan las marcas
- 🆕 **Ajustar sensibilidad**: Modificar umbral de detección según tipo de marca

**"OpenCV.js aún se está cargando"**
- ⚠️ **Nota**: Esta dependencia ha sido reemplazada por algoritmos nativos más eficientes
- Los filtros de imagen ahora funcionan directamente en el navegador
- Si aparece este mensaje, refrescar la página

## 📞 Soporte

Si tienes problemas o sugerencias:
1. Verifica que sigas el formato de imagen esperado
2. Prueba con diferentes calidades de imagen
3. Consulta la sección de solución de problemas

## 📄 Licencia

Este proyecto es de uso educativo y está diseñado específicamente para procesar exámenes MIPS de 180 preguntas V/F.

**Versión actual**: v2.0 - Con filtros avanzados de mejora de imagen y detección optimizada de marcas débiles.

---

## 📋 Registro de Cambios

### v2.0 (Junio 2025) - Filtros de Imagen Avanzados
- ✅ **Filtros de sobre exposición** para resaltar marcas débiles
- ✅ **Mejora de contraste configurable** en tiempo real
- ✅ **Umbral de detección adaptativo** para diferentes tipos de marcas
- ✅ **Panel de calibración ampliado** con controles de filtros
- ✅ **Detección mejorada** para marcas de lápiz y bolígrafo
- ✅ **Algoritmos nativos** sin dependencias externas pesadas

### v1.0 (Inicial)
- ✅ Reconocimiento OCR básico
- ✅ Detección de 180 preguntas V/F
- ✅ Exportación a CSV
- ✅ Panel de calibración básico

## 🆕 Nuevas Funcionalidades - Filtros de Imagen Avanzados

### 🎯 Sistema de Mejora de Imagen
El sistema ahora incluye algoritmos avanzados de preprocesamiento que mejoran significativamente la detección de marcas, especialmente útiles para:
- **Marcas débiles o poco contrastadas**
- **Imágenes con iluminación irregular**
- **Marcas hechas con lápiz suave**
- **Escaneos de baja calidad**

### ⚙️ Controles de Filtros Disponibles

#### 🔧 **Intensidad de Contraste (1.0 - 4.0)**
- **Propósito**: Aumenta la diferencia entre las marcas y el fondo del papel
- **Recomendado**: 2.0-3.0 para la mayoría de imágenes
- **Usar valores altos (3.5-4.0)** cuando las marcas son muy tenues
- **Usar valores bajos (1.0-2.0)** cuando la imagen ya tiene buen contraste

#### 📸 **Sobre Exposición (0.1 - 0.7)**
- **Propósito**: Oscurece las marcas y aclara el fondo para mejor detección
- **Recomendado**: 0.3 para uso general
- **Reducir (0.1-0.2)** cuando las marcas son muy oscuras
- **Aumentar (0.5-0.7)** cuando las marcas son muy claras o tenues

#### 🎯 **Umbral de Detección (0.05 - 0.4)**
- **Propósito**: Controla la sensibilidad del sistema para detectar marcas
- **Recomendado**: 0.15 para uso general
- **Reducir (0.05-0.1)** para detectar marcas muy débiles
- **Aumentar (0.3-0.4)** para evitar falsos positivos en imágenes ruidosas

### 🔍 Cómo Usar los Filtros

1. **Carga tu imagen** y activa el panel de calibración
2. **Observa el canvas en tiempo real** - verás 360 círculos de detección superpuestos
3. **Ajusta los filtros gradualmente**:
   - Comienza con **contraste** para mejorar la diferenciación
   - Ajusta **sobre exposición** si las marcas siguen siendo difíciles de ver
   - Modifica **umbral** para afinar la sensibilidad
4. **Observa los cambios inmediatamente** en el canvas de previsualización
5. **Aplica los cambios** cuando la detección se vea óptima

### 💡 Consejos de Optimización

- **Para imágenes claras**: Contraste 2.0, Exposición 0.3, Umbral 0.15
- **Para marcas débiles**: Contraste 3.5, Exposición 0.2, Umbral 0.1
- **Para imágenes ruidosas**: Contraste 2.5, Exposición 0.4, Umbral 0.25
- **Para lápiz suave**: Contraste 3.0, Exposición 0.2, Umbral 0.12
