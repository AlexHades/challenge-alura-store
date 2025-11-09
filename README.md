# Alura Store — Análisis Exploratorio y Comparativo de 4 Tiendas

> **¿De qué va este repo?**  
> Un análisis para evaluar el desempeño de cuatro tiendas de Alura Store con base en **ventas, mix de categorías, satisfacción del cliente y logística (envíos)**. El foco de este README es **explicar el análisis**, su **metodología**, las **métricas calculadas** y **cómo reproducirlo**.

---

## 🧭 Objetivos de análisis
1. **Cuantificar y comparar** el desempeño de cada tienda en:
   - Ingresos totales
   - Categorías más/menos vendidas
   - Calificación promedio de clientes
   - Productos más/menos vendidos
   - Costo de envío promedio
2. **Construir visualizaciones** que faciliten la comparación lateral (entre tiendas) y vertical (por categorías/productos).
3. **Estandarizar el flujo de trabajo** para que el análisis sea **reproducible** y **auditable**.

---

## 🗂️ Estructura del repositorio
```
.
├─ AluraStoreLatam.ipynb
└─ README.md
```

---

## 🔎 Preguntas guía (EDA)
- **Ingresos:** ¿Qué tienda factura más/menos
- **Categorías:** ¿Cuáles dominan el mix por tienda? ¿Hay concentración o portafolio equilibrado?
- **Satisfacción:** ¿Existen brechas relevantes en la calificación promedio entre tiendas?
- **Productos:** ¿Quién tiene superventas claros? ¿Qué tan “larga” es la cola de productos?
- **Logística:** ¿El costo de envío promedio varía de forma significativa entre tiendas?

---

## 🧪 Metodología (paso a paso)

### 1) Preparación de datos
- **Derivación de métricas base**:
  - `ingreso_tienda` = suma de ingresos por tienda.
  - `calificacion_promedio_tienda` = media de ratings por tienda.
  - `top_categorias_tienda` = ranking por volumen/ingresos.
  - `top_productos_tienda` = ranking por volumen/ingresos.
  - `costo_envio_promedio_tienda` = media por tienda.

### 2) Visualizaciones
- **Ingresos por tienda**: barras ordenadas.
- **Top categorías por tienda**: barras horizontales.
- **Calificación promedio por tienda**: barras ordenadas.
- **Top productos por tienda**: barras horizontales.
- **Costo de envío**: barras ordenadas.
  
---

## 🧩 Lógica de cálculos (ejemplos)
- **Ingresos totales por tienda**  
  `ingresos_tienda1 = tienda['Precio'].sum()`
  
- **Top categorías por tienda (por volumen)**  
  `ventas_por_categoria1 = tienda['Categoría del Producto'].value_counts()`
  
  `for i in range(1,5):
  print(f"Top 3 de categorías de la tienda {i}:")
  print(eval(f"ventas_por_categoria{i}").head(3))
  print()`
  
- **Calificación promedio**  
  `calificacion_promedio1 = tienda['Calificación'].mean()`
  
- **Costo de envío promedio**  
  `envio_promedio_tienda1 = tienda['Costo de envío'].mean()`

---

## 🚀 Cómo reproducir el análisis

### Opción A) Colab / Jupyter
1. Clona el repo y abre `AluraStoreLatam.ipynb`.
2. Ejecuta las celdas en orden.

### Opción B) Local (entorno recomendado)
- **Python**: 3.10+  
- **Paquetes** (mínimo): `pandas`, `matplotlib`, `seaborn`, `folium` 

```bash
# Crear entorno (opcional)
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -U pip
pip install pandas numpy matplotlib seaborn pyarrow
```
---

## 🧾 Notebooks
- `AluraStoreLatam.ipynb` — flujo principal del **EDA comparativo** y generación de gráficos.

---
## 🌐 Vista Web

Haz clic aquí para ver el notebook en línea:

➡️ **[Ver Notebook en NBViewer](https://nbviewer.org/github/AlexHades/challenge-alura-store/blob/master/AluraStoreLatam.ipynb)**
---

## 🤝 Contribuciones
¡Ideas y PRs son bienvenidos!  
Sugerencias típicas:
- Nuevas métricas (p. ej., **índice de concentración** por tienda).
- Limpieza/normalización de categorías.
- Dashboards adicionales (Power BI/Looker/Streamlit).

---

## 📄 Licencia
Este proyecto se publica con fines educativos. Ajusta la licencia según tus necesidades.
