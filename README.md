# 🚢 Alden: Sistema Predictivo de Riesgo Logístico Acuícola

Alden es un modelo de Machine Learning diseñado para optimizar la toma de decisiones en la logística marítima de la zona de Aysén y Los Lagos, Chile. El sistema predice el nivel de riesgo de las operaciones de despacho basándose en condiciones meteorológicas en tiempo real, coordenadas GPS específicas de los centros de cultivo y datos históricos de operación.

## 🚀 Características Principales
- **Precisión Geográfica:** Utiliza coordenadas GPS exactas para consultar microclimas en canales y fiordos.
- **Ajuste de Viento "Windy-Adapt":** Implementa un factor de corrección de seguridad (+2 kn y escala de 1.25) para igualar las condiciones críticas reportadas por la Armada de Chile y modelos como ECMWF.
- **Predicción Inteligente:** Basado en un Árbol de Decisión que considera 10 variables, incluyendo mareas (hora), ubicación y tipo de embarcación.

## 🛠️ Tecnologías Utilizadas
- **Lenguaje:** Python 3.x
- **Librerías:** Pandas, Scikit-Learn, Joblib, Requests.
- **API Clima:** Open-Meteo (Pronóstico global de alta resolución).

## 📁 Estructura del Proyecto
- `entrenamiento_alden.py`: Script para procesar el dataset histórico y generar el modelo `.pkl`.
- `asistente_alden.py`: Herramienta interactiva para la planificación de despachos diarios.
- `Vueltas.csv`: Dataset histórico con registros de gravedad y condiciones de navegación.

## 📊 Cómo Funciona
El modelo evalúa las siguientes variables para determinar la viabilidad del zarpe:
1. Zona y Centro de Destino (vía GPS).
2. Tipo de Embarcación.
3. Pronóstico de Viento, Lluvia y Temperatura.
4. Ventana horaria y día de la semana.
