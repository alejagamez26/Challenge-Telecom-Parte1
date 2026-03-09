# 📊 Telecom X — Análisis de Evasión de Clientes

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-lightgrey?logo=pandas)
![Colab](https://img.shields.io/badge/Google%20Colab-Notebook-orange?logo=googlecolab)
![Status](https://img.shields.io/badge/Estado-Completado-brightgreen)

---

## 📌 Propósito del Análisis

Telecom X enfrenta una tasa de cancelación del **26.5%** de sus clientes. Este proyecto aplica técnicas de **Análisis Exploratorio de Datos (EDA)** para identificar los factores que influyen en la evasión (*churn*), con el objetivo de apoyar al equipo de Data Science en el desarrollo de modelos predictivos y estrategias de retención.

**Preguntas clave que responde este análisis:**
- ¿Qué perfil de cliente tiene mayor probabilidad de cancelar?
- ¿Qué tipo de contrato o servicio está más asociado a la evasión?
- ¿Los clientes que se van pagan más o menos que los que se quedan?

---

## 🗂️ Estructura del Proyecto

```
telecom-x-churn/
│
├── TelecomX_Data.json         # Datos originales cargados desde la API
├── TelecomX_Analisis.ipynb    # Notebook principal con todo el análisis
└── README.md                  # Documentación del proyecto
```

---

## 🔄 Etapas del Proyecto

### 1. 📥 Carga de Datos
- Datos obtenidos desde una API pública en formato JSON
- Cargados con `pd.read_json()` y normalizados con `pd.json_normalize()`

### 2. 🧹 Limpieza y Transformación (ETL)

| Problema | Solución |
|---|---|
| Columnas anidadas | Aplanadas con `pd.json_normalize` |
| 224 registros con Churn vacío | Eliminados → 7,043 registros finales |
| `Charges.Total` en formato texto | Convertido a `float64` |
| Variables binarias en Yes/No | Convertidas a 1 y 0 |
| Columnas en inglés | Traducidas al español |
| Nueva variable | `Cuentas_Diarias` = cargo mensual / 30 |

### 3. 📊 Análisis Exploratorio (EDA)
- Distribución general de evasión
- Evasión por variables categóricas (género, contrato, método de pago, etc.)
- Evasión por variables numéricas (meses de contrato, cargos)

---

## 📈 Insights Principales

| Hallazgo | Detalle |
|---|---|
| 🔴 Contrato mes a mes | Mayor tasa de evasión de todos los grupos |
| 🔴 Fibra óptica | Alta evasión pese a ser servicio premium |
| 🔴 Cheque electrónico | Método de pago con más cancelaciones |
| 🔴 Clientes nuevos | La mayoría cancela en los primeros meses |
| 🟢 Contratos anuales/bianuales | Retienen significativamente más clientes |
| 🟢 Soporte técnico y seguridad online | Asociados a mayor fidelidad |

---

## 💡 Recomendaciones Estratégicas

1. **Incentivar contratos anuales** con descuentos desde el inicio
2. **Programa de bienvenida** enfocado en los primeros 3 meses
3. **Revisar precios o percepción de valor** del servicio de Fibra óptica
4. **Promover pagos automáticos** sobre cheque electrónico
5. **Ofrecer soporte técnico y seguridad** como servicios base del paquete

---

## ▶️ Instrucciones para Ejecutar el Notebook

### Opción A — Google Colab (recomendado)

1. Abre [Google Colab](https://colab.research.google.com/)
2. Ve a **Archivo → Subir notebook** y sube el archivo `TelecomX_Analisis.ipynb`
3. Ejecuta las celdas en orden con `Shift + Enter` o ve a **Runtime → Run all**

> Los datos se cargan automáticamente desde la URL de la API, no necesitas subir ningún archivo adicional.

### Opción B — Localmente con Jupyter

```bash
# 1. Clona o descarga el repositorio
git clone https://github.com/tu-usuario/telecom-x-churn.git
cd telecom-x-churn

# 2. Instala las dependencias
pip install pandas matplotlib seaborn

# 3. Abre el notebook
jupyter notebook TelecomX_Analisis.ipynb
```

---

## 🛠️ Tecnologías Utilizadas

- **Python 3.10+**
- **Pandas** — manipulación y limpieza de datos
- **Matplotlib** — visualizaciones
- **Seaborn** — gráficos estadísticos
- **Google Colab** — entorno de ejecución

---

## 👤 Autor

Análisis realizado como parte del programa de formación en Data Science.
**Telecom X — Challenge 2** 🚀
