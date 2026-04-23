# analisis-movilidad-urbana-latam
## 📊 Descripción del Proyecto
Análisis correlacional entre congestión vehicular y productividad económica en 15 ciudades latinoamericanas para el Banco de Desarrollo de América Latina.

## 🎯 Objetivos
- Identificar relación entre tráfico urbano y PIB per cápita
- Determinar ciudades prioritarias para inversión en infraestructura
- Proporcionar insights para políticas de movilidad urbana

## 🛠️ Herramientas Utilizadas
- Python (pandas, numpy, matplotlib, seaborn)
- Jupyter Notebooks
- Datos de TomTom Traffic API

## 📈 Resultados Principales
- [ Relación No Lineal - Contrario a la hipótesis inicial, no existe una correlación directa clara entre mayor PIB per cápita y mayor congestión. Los datos revelan patrones más complejos que requieren análisis multifactorial.
Segmentación por Desempeño .-Alto PIB + Baja Congestión: Montevideo (26,176 PIB, baja congestión) representa el modelo ideal .-Alto PIB + Alta Congestión: Ciudad de México (13,254 PIB, 2,833 min retraso) sugiere saturación de infraestructura .-Bajo PIB + Alta Congestión: Lima ($2,277 PIB, 1,052 min retraso) indica ineficiencias críticas.

Anomalías y Outliers Identificados Ciudad de México: Outlier extremo con 2,833 minutos de retraso promedio, significativamente superior al promedio LATAM (629 min). Requiere análisis profundo de sus estrategias de movilidad actuales. Bogotá: Combinación crítica de alta congestión (1,142 min) con PIB per cápita moderado (11,442), sugiriendo potencial económico limitado por problemas de movilidad. Fortaleza: Paradoja de baja congestión (50 min) pero segundo menor PIB per cápita(8,761), indicando que otros factores limitan el crecimiento económico.]

- [Prioridad Inmediata: Bogotá presenta la mejor relación costo-beneficio para inversión, combinando alta congestión con potencial económico demostrable. Investigación Adicional: Ciudad de México requiere estudio detallado para entender cómo mantiene productividad económica a pesar de congestión extrema. Benchmarking: Analizar las mejores prácticas de ciudades brasileñas como Brasília y Curitiba que muestran equilibrio favorable entre movilidad y productividad. Análisis Multivariable: Incorporar variables adicionales como densidad poblacional, políticas públicas y modelos económicos para explicar las anomalías identificadas]


## CODIGO UTILIZADO

# importe librerías
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

# cargue archivos
traffic = pd.read_csv('/datasets/tomtom_traffic.csv')
eco = pd.read_csv('/datasets/oecd_city_economy.csv') #completa el código

# mostre las primeras 5 filas de traffic
traffic.head()
Country	City	UpdateTimeUTC	JamsDelay	TrafficIndexLive	JamsLengthInKms	JamsCount	TrafficIndexWeekAgo	UpdateTimeUTCWeekAgo	TravelTimeLivePer10KmsMins	TravelTimeHistoricPer10KmsMins	MinsDelay
0	ARE	abu-dhabi	2025-01-13 04:01:30.001	650.7	36.0	109.1	162.0	30.0	2025-01-06 04:01:30.000	11.614767	10.265330	1.349437
1	ARE	abu-dhabi	2025-01-13 03:46:00.000	540.4	30.0	101.4	136.0	27.0	2025-01-06 03:46:30.001	11.003180	10.031544	0.971635
2	ARE	abu-dhabi	2025-01-13 02:46:30.000	71.8	7.0	18.9	23.0	6.0	2025-01-06 02:46:30.000	8.196278	8.196510	-0.000232
3	ARE	abu-dhabi	2025-01-13 01:46:30.001	8.2	2.0	4.1	2.0	2.0	2025-01-06 01:46:30.000	7.723808	7.899046	-0.175238
4	ARE	abu-dhabi	2025-01-13 00:01:30.000	1.1	1.0	0.2	1.0	1.0	2025-01-06 00:01:30.000	8.336363	8.604379	-0.268016

# mostre las primeras 5 filas de eco
eco.head()
Year	City	Country	City GDP/capita	Unemployment %	PM2.5 (μg/m³)	Population (M)
0	2023	buenos-aires	Argentina	15.782,00	6.2%	15,2	15,30
1	2023	sao-paulo	Brazil	14.475,00	9.1%	29,50	22,50
2	2023	rio-de-janeiro	Brazil	13.142,00	9.8%	19,10	13,60
3	2023	brasilia	Brazil	15.999,00	8.3%	13,50	4,70
4	2023	salvador	Brazil	8.761,00	13.1%	16,00	3,90




