# Preprocesamiento y Modelamiento de Datos - Satisfacción del Cliente

**Proyecto desarrollado para la formación SENA - Curso 21710120**  
**Estudiante**: David Francisco Gil Castaldo - CE 607688  
**Fecha**: Noviembre 2025  
**Evidencia**: AA1-EV03 - Informe Técnico de Preprocesamiento y Modelamiento de Datos 

## Contexto del Proyecto

Este proyecto aborda la preparación de datos para un **modelo de regresión que predice SatisfactionScore** en un servicio de streaming. El dataset contiene información de clientes con problemas de calidad identificados: inconsistencias categóricas, valores nulos, outliers y formatos heterogéneos de fechas.

## Objetivo

**Preparar dataset crudo para modelado predictivo** mediante limpieza, transformación e ingeniería de features, siguiendo el plan detallado en el informe técnico del SENA.

## Dataset Original

**`customer_satisfaction_data.csv`**
- **Registros**: 1,000 
- **Variables**: 8 originales 
  - `CustomerID`: Identificador único (string)
  - `Age`: Edad cliente (outliers 0-145) 
  - `PlanType`: Tipo de plan (inconsistencias: Premium/premium/PREM) 
  - `MonthlyBill`: Factura mensual (~15% valores nulos) 
  - `HoursWatchedLast30d`: Horas visualizadas
  - `SignupDate`: Fecha alta (formatos variados)
  - `CustomerCode`: Código cliente
  - `LastSupportTicket`: Texto libre tickets soporte

## Metodología Aplicada

### 1. Análisis Inicial y Diagnóstico
Identificación problemas: nulos en MonthlyBill (15%), outliers Age, inconsistencias PlanType

Diccionario de datos documentado

text

### 2. Limpieza y Transformación
✅ Unificación PlanType: minúsculas + strip() + replace('prem/premi' → 'premium')
✅ Conversión SignupDate → datetime con try_parse()
✅ Truncamiento outliers Age: clip(10, 100)
✅ Imputación MonthlyBill: mediana
✅ Label Encoding PlanType: básico=0, estándar=1, premium=2
✅ Creación feature: AntiguedadCliente (meses desde SignupDate)

text

### 3. Normalización
MinMaxScaler en MonthlyBill y HoursWatchedLast30d

Escalado para reducir impacto outliers

text

## Tecnologías
import pandas as pd
from dateutil.parser import parse
from sklearn.preprocessing import MinMaxScaler
from datetime import datetime.
