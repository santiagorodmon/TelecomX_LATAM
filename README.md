# 📊 Análisis de Evasión de Clientes — Telecom X

Proyecto de análisis exploratorio de datos (EDA) orientado a entender el comportamiento de evasión (*churn*) de clientes de una empresa de telecomunicaciones ficticia. El objetivo es identificar los factores que más influyen en la cancelación del servicio y proponer estrategias de retención basadas en los datos.

---

## 📁 Estructura del proyecto

```
📦 telecom-x-churn
 ┣ 📓 01_extraccion_datos.ipynb   # Notebook principal: extracción, limpieza y EDA
 ┗ 📄 README.md
```

---

## 📌 Descripción del notebook

El notebook cubre las siguientes etapas:

1. **Importación de librerías y datos** — Carga del dataset en formato JSON desde un repositorio público.
2. **Exploración inicial** — Revisión de dimensiones, tipos de datos y estructura del dataset.
3. **Desanidado de columnas** — Normalización de columnas con datos en formato diccionario (`customer`, `phone`, `internet`, `account`).
4. **Limpieza y tratamiento de datos**
   - Verificación de nulos y duplicados
   - Conversión de tipos (`Charges.Total` a numérico)
   - Imputación de nulos en clientes nuevos (`tenure = 0`)
   - Creación de la variable `Valor_Diario`
   - Estandarización de columnas (traducción al español, codificación binaria)
   - Eliminación de registros con evasión nula (3% del total)
5. **Análisis exploratorio (EDA)**
   - Estadísticas descriptivas de variables numéricas
   - Boxplots de variables numéricas por evasión
   - Análisis de variables categóricas (género, tipo de contrato, método de pago, etc.)
   - Análisis de servicios adicionales (seguridad, soporte, streaming, etc.)
   - Tasa de evasión por rangos de antigüedad
   - Matriz de correlación
6. **Conclusiones y recomendaciones estratégicas**

---

## 📊 Dataset

- **Fuente:** [TelecomX_Data.json](https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json)
- **Registros:** 7,267 clientes (7,043 tras limpieza)
- **Variables principales:** antigüedad, cargo mensual, cargo total, tipo de contrato, método de pago, servicios contratados, tipo de internet, evasión.

---

## 🔍 Principales hallazgos

| Factor | Observación |
|---|---|
| **Antigüedad** | Clientes que evaden tienen mediana de 30 meses vs. 60 en los que permanecen |
| **Cargo mensual** | Quienes evaden pagan más (~$80 vs ~$40 de mediana) |
| **Tipo de contrato** | Evasión mensual: 42.7% · Anual: 11.3% · Bianual: 2.8% |
| **Método de pago** | Cheque electrónico: 38.4% de evasión vs. ~15-17% en pagos automáticos |
| **Servicios adicionales** | Sin soporte/seguridad: 30-35% de evasión vs. ~15% con servicios |
| **Tipo de internet** | Fibra óptica: 35.5% · DSL: 19.6% · Sin internet: 7.2% |

**Perfil de alto riesgo:** cliente con contrato mensual, fibra óptica, pago con cheque electrónico, sin servicios de soporte/seguridad, baja antigüedad (<20 meses) y cargo mensual elevado.

---

## 💡 Recomendaciones estratégicas

1. **Incentivar contratos de larga duración** con descuentos o beneficios exclusivos.
2. **Promover el pago automático** mediante pequeños descuentos por domiciliación.
3. **Crear bundles de valor** que incluyan soporte técnico y seguridad online, especialmente para clientes nuevos.
4. **Alertas tempranas** para clientes con menos de 12 meses de antigüedad y cargo mensual alto.
5. **Revisar la propuesta de fibra óptica**: analizar calidad del servicio o aplicar promociones en este segmento.
6. **Campañas de retención segmentadas** dirigidas a los perfiles de mayor riesgo identificados.

---

## 🛠️ Tecnologías utilizadas

- Python 3
- [pandas](https://pandas.pydata.org/)
- [numpy](https://numpy.org/)
- [matplotlib](https://matplotlib.org/)
- [seaborn](https://seaborn.pydata.org/)

---

## ▶️ Cómo ejecutar

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/telecom-x-churn.git
   cd telecom-x-churn
   ```

2. Instala las dependencias:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

3. Abre el notebook:
   ```bash
   jupyter notebook 01_extraccion_datos.ipynb
   ```

   También puedes abrirlo directamente en [Google Colab](https://colab.research.google.com/).

---

## 📄 Licencia

Este proyecto fue desarrollado con fines educativos como parte del **Challenge 2 — Data Science LATAM**.
