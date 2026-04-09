# Segmentación de Clientes - Quantum Retail

## 📋 Descripción del proyecto

**AA2-EV02: Segmentación y evaluación de clientes mediante PCA y K-Means** para Quantum Retail, empresa que lanza *Aura Pro* (audio inmersivo).

Objetivo: Identificar **3 segmentos de clientes** para campañas de marketing dirigidas, optimizando costos. Dataset `quantum_customer_data.csv` (1000 clientes, 10 variables: Age, AnnualIncome, SpendingScore, WebVisits, etc.).

**Pipeline técnico**:
```
EDA → StandardScaler → PCA (9 componentes, 91% varianza) → K-Means (k=3) → Perfiles de negocio
```

## 📊 Resultados

**Distribución segmentos** (equilibrada): 35.6% | 34.9% | 29.5%  [ppl-ai-file-upload.s3.amazonaws]

| Segmento  | % Clientes  | Perfil clave                       | Estrategia marketing |
|-----------|-------------|------------------------------------|----------------------|
| **0**     | 356 (35.6%) | Alto ingreso/gasto, riesgo churn   | Reactivación VIP     |
| **1**     | 349 (34.9%) | Fieles digitales, carritos grandes | Cross-selling email  |
| **2**     | 295 (29.5%) | Bajo valor, carritos pequeños      | Upselling básico     |

**Métricas técnicas**:
- **PCA**: 91% varianza con 9 componentes
- **K-Means**: Codo en k=3 (método WCSS)

## 🛠️ Stack tecnológico

```python
pandas      # EDA, manipulación
scikit-learn # StandardScaler, PCA, K-Means
matplotlib   # Varianza, boxplots
seaborn     # Correlaciones, perfiles
numpy       # Cálculos
```

## 📂 Estructura del proyecto

```
quantum-retail-segmentation/
├── AA2_EV01.ipynb                           # EDA + dataset 
├── Segmentacion-y-evaluacion-de-clientes... # Informe completo 
├── quantum_customer_data.csv                # 1000x11 dataset 
└── README.md                               # Documentación
```

## 🚀 Instalación y ejecución

```bash
# Dependencias
pip install pandas numpy scikit-learn matplotlib seaborn jupyter

# Ejecutar análisis
jupyter notebook AA2_EV01.ipynb
```

**Reproducibilidad**: `np.random.seed(42)

## 🎯 Impacto de negocio

**Recomendaciones implementadas**:
```
Segmento 0 → Ofertas exclusivas Aura Pro (reactivación)
Segmento 1 → Bundles + email marketing (cross-selling)  
Segmento 2 → Promociones entrada (aumentar ticket promedio)
```

## 📈 Visualizaciones generadas

- **EDA**: Descriptivas, correlaciones, skewness
- **PCA**: Scree plot (varianza acumulada)
- **Clustering**: Elbow curve, boxplots por segmento
- **Perfiles**: Medias variables por cluster

## 🎓 Contexto académico

```
Curso: 21710120 - Gestión de Datos en Modelos de IA (SENA)
Estudiante: David Francisco Gil Castaldo, CE 607688
Fecha: Diciembre 2025
```

## 💼 Habilidades demostradas

✅ **Data Science**: EDA completo, reducción dimensional, clustering  
✅ **ML**: PCA (91% varianza), K-Means (k=3 óptimo)  
✅ **Negocio**: Perfiles accionables + recomendaciones marketing  
✅ **Comunicación**: Informe ejecutivo (PDF) + código reproducible  

***

