# ETL con IA Generativa - Customer Satisfaction

## 📋 Descripción del proyecto

**AA2-EV01: Formulación de prompts para IA generativa en integración de datos** del dataset `customer_satisfaction_data.csv` (servicio de streaming)

**Objetivo**: Automatizar ETL (Extract, Transform, Load) para predecir `SatisfactionScore` usando **ChatGPT prompts**. Preparación de datos crudos para regresión.

**Problemas detectados**:
- `Age`: Outliers (0, 110+)
- `PlanType`: Inconsistencias ("premium", "Premium", "PREM")
- `MonthlyBill`: 15 nulos
- `SignupDate`: Formatos mixtos (20230521, 15-Mar-2022)
- `LastSupportTicket`: Texto libre no estructurado 

## 🛠️ Pipeline automatizado (3 prompts)

**Prompt 1**: Limpieza categóricas/numéricas
```
✅ Estandariza PlanType → One-Hot Encoding
✅ Imputa MonthlyBill → mediana  
✅ Filtra Age outliers (18-100)
```

**Prompt 2**: Feature Engineering temporal
```
✅ Unifica SignupDate → datetime
✅ Nueva feature: AntiguedadMeses (hasta 2025-12-11)
✅ PromedioHorasMensual = HoursWatchedLast30d / AntiguedadMeses
```

**Prompt 3**: Procesamiento texto 
```
✅ Extrae keywords de LastSupportTicket
✅ Categoriza: Técnico/Contenido/Cobro/Desconocido
✅ Top keywords + validación sesgos
```

## 📊 Impacto en calidad de datos

| Prompt | Cambios clave               | Mejora calidad            |
|---------|----------------------------|---------------------------|
| **1**   | +20% consistencia, 0 nulos | Completitud/consistencia  |
| **2**   | +2 features derivadas      | Validez temporal          |
| **3**   | Texto → categórica         | Reducción dimensionalidad |

**Ética**: Minimización datos sensibles, validación manual sesgos 

## 📂 Estructura del proyecto

```
customer-satisfaction-etl/
├── AA2-EV01-Informe-de-formulacion-de-prompts.pdf  # Documentación completa 
├── customer_satisfaction_data.csv                   # Dataset original 
└── README.md                                       # Este archivo
```

## 🎯 Resultados de prompts

**Ejemplo Prompt 2 (antes/después)**:
| CustomerID | SignupDate **antes** | **después** | AntiguedadMeses | PromedioHorasMensual |
|------------|----------------------|-------------|-----------------|----------------------|
| fila 1     | 20230521             | 2023-05-21  | 31.6            | 1.14                 |
| fila 2     | 20251020             | 2025-10-20  | 1.7             | 13.89                |

## 🎓 Contexto académico

```
Curso: 21720207 - Aplicación IA en Integración de Datos (SENA)
Estudiante: David Francisco Gil Castaldo, CE 607688
Fecha: Diciembre 2025
```

## 💼 Habilidades demostradas

✅ **Prompt Engineering**: 3 prompts estructurados (rol+contexto+output)  
✅ **ETL automatizado**: Limpieza + FE + texto con IA generativa  
✅ **Data Quality**: Manejo nulos/outliers/inconsistencias  
✅ **Ética IA**: Minimización datos, validación sesgos  
✅ **Streaming Analytics**: Features para churn/satisfacción  

