# 📘 Documentación Técnica — Proyecto Parte 2  
### Árboles de Decisión • Random Forest • Redes Neuronales

**Autor:** Linda Esmeralda Nohemí Morales Donis  

### **Lenguajes utilizados**
- **R** → Árboles de Decisión y Random Forest  
- **Python** → Redes Neuronales  

### **Entornos de desarrollo**
- **RStudio (2024+)**  
- **Google Colab (Python 3.10 / TensorFlow 2.15)**  

### **Tipo de proyecto:**  
Modelos predictivos aplicados a datos del Ministerio Público (2018–2024).

---

# 1. 📄 Descripción General

Este documento describe la **configuración técnica**, **ejecución** y **replicación completa** del Proyecto Parte 2, el cual implementa tres enfoques predictivos:

- **Árboles de Decisión – R**  
- **Random Forest (Bosques Aleatorios) – R**  
- **Redes Neuronales Artificiales (ANN) – Python / TensorFlow**

El objetivo principal es predecir variables clave relacionadas con el fenómeno delictivo en Guatemala:

- **Grupo etario (`grupo_edad`)**  
- **Tipo de delito (`delito`)**  
- **Zona de ocurrencia (`zona`)**

Estas predicciones se basan en los datos del MP previamente estandarizados y unidos en la Parte 1 del proyecto.

---

# 2. 🖥️ Requisitos del Entorno

## 2.1 Versiones de los Lenguajes

### **R**
- Recomendado: **R ≥ 4.3**  
- Asegura compatibilidad con `rpart`, `randomForest` y `dplyr`.

### **Python**
- Recomendado: **Python ≥ 3.10**  
- Google Colab sugerido (GPU opcional).

---

## 2.2 Software Requerido

### 🟦 **RStudio (2023.09 o superior)**
IDE recomendado para ejecutar los modelos en R.

### 🟨 **Google Colab**
Requerido para el entrenamiento de redes neuronales sin sobrecargar la computadora local.

---

## 2.3 Librerías Requeridas  

---

### **En R**

| Librería       | Descripción                    | Uso principal             |
|----------------|--------------------------------|---------------------------|
| `dplyr`        | Manipulación de datos          | Limpieza y estandarización |
| `readxl`       | Lectura de archivos Excel      | Cargar datasets del MP     |
| `rpart`        | Árboles de decisión            | Primer modelo predictivo   |
| `rpart.plot`   | Visualización del árbol        | Gráficos interpretativos   |
| `randomForest` | Bosques aleatorios             | Segundo modelo predictivo  |

**Instalación:**

```r
install.packages(c("dplyr","readxl","rpart","rpart.plot","randomForest"))
```

## 2.4 En Python (Google Colab)

### Librerías utilizadas

| Librería      | Uso                                         |
|---------------|----------------------------------------------|
| pandas        | Lectura y manipulación de datos             |
| scikit-learn  | Escalado, train/test split, codificación    |
| tensorflow    | Redes neuronales (Keras)                    |
| numpy         | Operaciones numéricas                       |

### Instalación

```bash
!pip install tensorflow scikit-learn pandas numpy
```
## 3. 📂 Carga y Unificación del Dataset

### Código base en R

```r
library(readxl)
library(dplyr)

# archivos del MP 2018–2024
# Se estandarizan, renombran y unen en un solo dataframe
datos <- bind_rows(dt2018, dt2019, dt2020, dt2021, dt2022, dt2023, dt2024)
```
## 4. 📌 Comparación entre los 3 modelos

| Modelo            | Ventajas                | Desventajas            | Cuándo usarlo            |
|------------------|-------------------------|-------------------------|---------------------------|
| Árbol            | Fácil de interpretar    | Menor precisión         | Auditorías internas       |
| Random Forest    | Muy robusto             | Poco interpretable      | Grandes datasets          |
| Redes Neuronales | Alta generalización     | Requiere más recursos   | Predicciones complejas    |

---

## 5. 📘 Diccionario de Variables Utilizadas

### Variable: `grupo_edad`

| Código | Rango   |
|--------|---------|
| 1      | 0–4     |
| 2      | 5–9     |
| 3      | 10–14   |
| 4      | 15–19   |
| 5      | 20–24   |
| 6      | 25–29   |
| 7      | 30–34   |
| 8      | 35–39   |
| 9      | 40–44   |
| ...    | ...     |

---

### Variable: `delito`

> Debido a la gran cantidad de códigos, no se incluyen.





