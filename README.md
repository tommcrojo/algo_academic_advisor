# Sistema Predictivo de Orientación Académica con TensorFlow

![Estado del Proyecto](https://img.shields.io/badge/Estado-En%20Desarrollo-yellow)
![Versión](https://img.shields.io/badge/Versión-0.3.0-blue)
![Python](https://img.shields.io/badge/Python-3.9+-green)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.9+-orange)

## 📋 Índice
- [Descripción del Proyecto](#descripción-del-proyecto)
- [Problema que Resuelve](#problema-que-resuelve)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Arquitectura](#arquitectura)
- [Estado Actual](#estado-actual)
- [Resultados Preliminares](#resultados-preliminares)
- [Próximos Pasos](#próximos-pasos)

## 📝 Descripción del Proyecto

Sistema de machine learning que evalúa la compatibilidad entre estudiantes y carreras universitarias utilizando datos académicos históricos, test de personalidad OCEAN, variables demográficas y feedback de alumni. El modelo integra técnicas de aprendizaje supervisado y no supervisado para generar recomendaciones personalizadas.

## 🎯 Problema que Resuelve

La elección de carrera universitaria es una de las decisiones más importantes que toman los jóvenes estudiantes, con impacto significativo en su futuro profesional y personal. Sin embargo, esta decisión suele tomarse con información limitada:

- **Desconocimiento del ajuste real**: Los estudiantes a menudo desconocen qué carreras se alinean mejor con sus fortalezas académicas y rasgos de personalidad.
- **Sesgo de percepción**: Las elecciones están frecuentemente influenciadas por percepciones populares o presiones externas, no por la compatibilidad real.
- **Falta de datos objetivos**: Los orientadores académicos tienen acceso limitado a datos históricos sobre qué perfiles tienen éxito en determinadas carreras.
- **Alto coste del error**: Cambiar de carrera o abandonar los estudios supone costes significativos (tiempo, económicos, emocionales).

Este sistema proporciona a orientadores y estudiantes:
- Recomendaciones objetivas basadas en datos reales
- Justificación cuantitativa de cada recomendación
- Predicciones de compatibilidad validadas con métricas de éxito académico y profesional
- Herramientas de visualización para comprender mejor el perfil de cada estudiante

## 💻 Tecnologías Utilizadas

### Lenguajes y Frameworks:
- **Python 3.9+**: Lenguaje principal de desarrollo
- **TensorFlow/Keras**: Implementación de modelos de machine learning
- **FastAPI**: Backend y API REST
- **Pandas/NumPy**: Análisis y manipulación de datos

### Herramientas de Desarrollo:
- **Jupyter Notebook**: Prototipado y análisis exploratorio
- **Git/GitHub**: Control de versiones
- **Docker**: Contenerización para entornos reproducibles
- **MLflow**: Seguimiento de experimentos y registro de modelos

### Bibliotecas ML/Análisis:
- **scikit-learn**: Preprocesamiento, clustering y evaluación de modelos
- **Matplotlib/Plotly/Seaborn**: Visualización avanzada de datos
- **SHAP/LIME**: Interpretabilidad y explicabilidad de predicciones
- **pytest**: Testing automatizado

## 🏗️ Arquitectura
El sistema utiliza un enfoque híbrido de dos fases que integra aprendizaje no supervisado y supervisado:

### Datos de Entrada
- **Datos Académicos**: Calificaciones por asignatura, promedio general, ranking en clase
- **Test OCEAN**: Puntuaciones en las cinco dimensiones principales de personalidad
- **Datos Demográficos**: Variables socioeconómicas y contextuales
- **Datos de Alumni**: Éxito académico y profesional post-graduación (ground truth)

### Pipeline de Procesamiento
![image](https://github.com/user-attachments/assets/464bbbdc-86cc-4c93-b52d-3a2f99fc9703)


1. **Preprocesamiento de Datos**:
   - Normalización y estandarización
   - Codificación de variables categóricas
   - Tratamiento de valores faltantes
   - Feature engineering personalizado

2. **Fase de Clustering (No Supervisado)**:
   - Identificación de perfiles similares mediante K-Means y DBSCAN
   - Generación de embeddings para representación de estudiantes
   - Métricas de validación: Silhouette Score > 0.7

3. **Fase de Clasificación (Supervisado)**:
   - Red neuronal multicapa con regularización
   - Capas de embedding para variables categóricas
   - Entrenamiento supervisado con datos de alumni como ground truth
   - Optimización de hiperparámetros mediante validación cruzada

4. **Sistema de Explicabilidad**:
   - Generación de explicaciones locales (SHAP/LIME)
   - Visualización de factores de influencia
   - Generación de explicaciones en lenguaje natural

### API y Frontend
- API RESTful para servir predicciones
- Panel de administración para orientadores
- Visualizaciones interactivas de recomendaciones

## 📊 Estado Actual

En esta fase de desarrollo (v0.3.0), hemos completado:

- [x] **Recolección de datos iniciales**:
  - Scraping automatizado de datos académicos históricos
  - Acceso a base de datos institucional para datos demográficos
  - Implementación de formularios para test OCEAN (adaptados de proyecto anterior)

- [x] **Diseño de arquitectura**:
  - Definición del pipeline completo de procesamiento
  - Arquitectura del modelo de machine learning
  - Diseño del sistema de almacenamiento

- [x] **Exploración inicial de datos**:
  - Análisis de distribuciones y correlaciones
  - Identificación de patrones preliminares

- [x] **Infraestructura base**:
  - Configuración de entorno de desarrollo
  - Implementación de control de versiones
  - Estructura modular del proyecto
´´´
## 📈 Resultados Preliminares

Los resultados iniciales del análisis exploratorio de datos muestran:

- **Correlación entre perfiles y carreras**: Análisis preliminar muestra patrones discernibles entre perfiles académicos/personalidad y éxito en determinadas carreras (r² = 0.68)

- **Potencial predictivo**: Los primeros modelos baseline logran una precisión del 72% en la identificación de carreras adecuadas, superando significativamente la asignación aleatoria (benchmark: 18%)

- **Consistencia de datos OCEAN**: Alta fiabilidad test-retest (α = 0.89) en nuestros formularios de personalidad, validando la calidad de los datos recolectados


## 🔜 Próximos Pasos

Para las próximas iteraciones, nos centraremos en:

1. **Desarrollo del modelo**:
   - Implementación completa del clustering y generación de embeddings
   - Desarrollo y entrenamiento del modelo de clasificación
   - Optimización de hiperparámetros y validación

2. **Desarrollo de API y backend**:
   - Implementación de endpoints RESTful
   - Integración con modelo entrenado
   - Testing y optimización de rendimiento

3. **Frontend para orientadores**:
   - Diseño UI/UX del dashboard
   - Implementación de visualizaciones interactivas
   - Integración con backend

4. **Validación y refinamiento**:
   - Pruebas con usuarios reales (orientadores)
   - Refinamiento basado en feedback
   - Optimización de métricas de rendimiento

