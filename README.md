# Propiedades_Inmobiliarias
Propiedades_Inmobiliarias

## 🎯 Objetivos del proyecto

1. Entender la estructura de **Unity Catalog** (Catálogo → Esquema → Tabla/Volume)
2. Crear tu propio **catálogo, esquema y volume**
3. Cargar datos crudos desde un CSV
4. Realizar un **EDA (Exploratory Data Analysis)** completo
5. Aplicar **CTEs** y **Window Functions** en análisis real
6. Identificar problemas de calidad de datos

---

## 📊 Dataset: Propiedades Inmobiliarias

Trabajaremos con datos **reales y crudos** de propiedades inmobiliarias scrapeadas de:
- ZonaProp
- MercadoLibre
- Argenprop

## Jerarquía de Unity Catalog

bootcamp
    ├── landing
    │       └── archivos (volume para CSVs - simula data lake)
    └── bronze
            └── properties_bronze (tabla con datos crudos)

## 📚 Tablas MANAGED vs EXTERNAL

### MANAGED TABLE (Tabla Administrada)
- Databricks **controla tanto los metadatos como los datos**


### EXTERNAL TABLE (Tabla Externa)
- Databricks **solo controla los metadatos**
- Los datos viven en una ubicación externa (S3, ADLS, etc.)
- Si borras la tabla, **los datos NO se borran**

### ¿Cuándo usar cada una?

| Escenario | Tipo recomendado |
|-----------|------------------|
| Datos crudos/bronze | EXTERNAL |
| Datos procesados (silver/gold) | MANAGED |
| Archivos compartidos entre equipos | EXTERNAL |
| Tablas temporales de análisis | MANAGED |
| Datos que vienen de otro sistema | EXTERNAL |
