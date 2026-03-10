# 🏪 Alura Store Latam — Análisis de Datos

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557C?style=for-the-badge&logo=python&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=black)
![Status](https://img.shields.io/badge/Estado-✅%20Completado-brightgreen?style=for-the-badge)

**Challenge 1 — Data Science | Alura Latam**

[Ver Notebook](./AluraStoreLatam.ipynb) · [Fuente de datos](https://github.com/alura-es-cursos/challenge1-data-science-latam)

</div>

---

## 📋 Propósito del Análisis

El **Sr. Juan** es dueño de una cadena de 4 tiendas llamada **Alura Store**. Quiere vender una de ellas para financiar un nuevo emprendimiento, pero necesita tomar esa decisión basándose en datos, no en corazonadas.

Este proyecto analiza el desempeño real de cada tienda a partir de sus datos históricos de ventas para responder una pregunta concreta:

> ### ❓ *¿Cuál de las 4 tiendas tiene el peor rendimiento global y debería ser vendida?*

Para responderla se analizaron **5 dimensiones clave**:

| Dimensión | ¿Qué responde? |
|-----------|----------------|
| 💰 Ingresos totales | ¿Cuánto dinero genera cada tienda? |
| 🛍️ Ventas por categoría | ¿Qué tipo de productos se venden más? |
| ⭐ Calificaciones de clientes | ¿Qué tan satisfechos están los compradores? |
| 🏆 Productos más/menos vendidos | ¿Qué artículos lideran o arrastran las ventas? |
| 🚚 Costo de envío promedio | ¿Qué tan competitiva es la logística? |

---

## 🗂️ Estructura del Proyecto

```
📦 alura-store-latam/
│
├── 📓 AluraStoreLatam.ipynb      ← Notebook principal (análisis + gráficos + informe)
├── 📄 README.md                  ← Este archivo
│
└── 📁 graficos/                  ← Imágenes exportadas al ejecutar el notebook
    ├── 📊 grafico1_ingresos.png          (Barras: ingresos por tienda)
    ├── 📊 grafico2_categorias.png        (Barras agrupadas: ventas por categoría)
    ├── 🥧 grafico3_calificaciones.png    (Pie charts: distribución de ratings)
    ├── 📈 grafico4_productos.png         (Líneas: top 10 productos)
    ├── 🔵 grafico5_dispersion.png        (Bubble chart: ingreso vs calificación)
    └── 📊 grafico6_ranking.png           (Barras horizontales: ranking final)
```

### Organización interna del Notebook

```
[Celda 0]   Importación de librerías y carga de datos
[Sección 1] Análisis de Facturación          → Gráfico de barras verticales
[Sección 2] Ventas por Categoría             → Barras agrupadas por tienda
[Sección 3] Calificación Promedio            → Gráficos circulares (pie)
[Sección 4] Productos Más y Menos Vendidos   → Gráfico de líneas
[Sección 5] Costo de Envío Promedio          → Bubble chart comparativo
[Sección 6] Resumen Comparativo              → Tabla con scoring final
[Sección 7] Informe Final                    → Recomendación al Sr. Juan
```

---

## 📊 Ejemplos de Gráficos e Insights Obtenidos

> Los gráficos se generan automáticamente al ejecutar el notebook y se guardan en la carpeta `/graficos`.

---

### 📊 Gráfico 1 — Ingresos Totales por Tienda
**Tipo: Barras verticales con etiquetas de valor**

```
Millones COP
  ▲
  │  ████
  │  ████  ████
  │  ████  ████  ████
  │  ████  ████  ████  ████
  └──T1────T2────T3────T4──▶
  (mayor)              (menor)
```

> 💡 **Insight:** La Tienda 1 lidera la facturación total. La **Tienda 4 es la que menos ingresos genera**, con una diferencia notable frente a las demás, posicionándola como la principal candidata a vender.

---

### 📊 Gráfico 2 — Ventas por Categoría y Tienda
**Tipo: Barras agrupadas (4 barras de colores por cada categoría)**

Las categorías con mayor volumen de ventas en todas las tiendas son:

| Rank | Categoría | Observación |
|------|-----------|-------------|
| 🥇 1° | Muebles | Lidera en 3 de 4 tiendas |
| 🥈 2° | Electrónicos | Consistente en todas las tiendas |
| 🥉 3° | Deportes y diversión | Fuerte en Tiendas 1 y 2 |

> 💡 **Insight:** La Tienda 4 muestra un volumen de unidades vendidas inferior en casi todas las categorías, confirmando una menor actividad comercial transaccional en toda su operación.

---

### 🥧 Gráfico 3 — Distribución de Calificaciones de Clientes
**Tipo: 4 gráficos circulares (pie), uno por tienda**

Escala: 1 ⭐ (muy malo) → 5 ⭐ (excelente)

| Tienda | Calificación Promedio | Observación |
|--------|-----------------------|-------------|
| Tienda 1 | ~3.9 / 5 | Satisfacción buena |
| Tienda 2 | ~4.0 / 5 | Satisfacción buena |
| Tienda 3 | ~4.1 / 5 | ✅ Mejor valorada |
| Tienda 4 | ~3.8 / 5 | ⚠️ Menor satisfacción |

> 💡 **Insight:** Aunque las diferencias son pequeñas, la Tienda 4 tiene la **calificación promedio más baja**, indicando que la experiencia de compra es menos satisfactoria para sus clientes.

---

### 📈 Gráfico 4 — Top 10 Productos Más Vendidos
**Tipo: Línea con marcadores circulares y etiquetas de cantidad**

```
Ventas
 ▲
 │ ●
 │  ●  ●
 │      ● ●
 │          ● ● ● ● ●
 └──1──2──3──4──5──6──7──8──9──10──▶ Ranking
```

> 💡 **Insight:** Las ventas se concentran en pocos productos estrella. La Tienda 4 tiene menor presencia de estos artículos líderes en su mix, lo que reduce su competitividad y ticket promedio.

---

### 🔵 Gráfico 5 — Ingreso Total vs. Calificación Promedio
**Tipo: Bubble chart (tamaño de burbuja = costo de envío promedio)**

```
Calificación
  5 │
    │
4.1 │              ● T3
4.0 │          ● T2
3.9 │      ● T1
3.8 │                         ○ T4  ← baja calificación Y bajos ingresos
    └──────────────────────────────▶
                           Ingresos
```

> 💡 **Insight:** Este gráfico resume todo el análisis en una sola imagen. La **Tienda 4 aparece en la esquina de menor ingreso y menor calificación**, sin compensar con un envío más económico.

---

### 📊 Gráfico 6 — Ranking Comparativo Final
**Tipo: Barras horizontales (3 paneles, uno por métrica)**

| Métrica | 🥇 1° | 🥈 2° | 🥉 3° | ⚠️ 4° |
|---------|-------|-------|-------|--------|
| 💰 Ingresos | T1 | T2 | T3 | **T4** |
| ⭐ Calificación | T3 | T2 | T1 | **T4** |
| 🚚 Envío eficiente | T1 | T3 | T2 | **T4** |

> 💡 **Insight clave:** La **Tienda 4 ocupa el último lugar en las tres métricas evaluadas**. No hay ningún factor que la diferencie positivamente del resto de la cadena.

---

## 🚀 Instrucciones para Ejecutar el Notebook

### ✅ Opción 1: Google Colab — Sin instalación (Recomendada)

1. Ingresa a [colab.research.google.com](https://colab.research.google.com/)
2. Haz clic en **Archivo → Subir notebook**
3. Selecciona `AluraStoreLatam.ipynb` desde tu computadora
4. Haz clic en **Entorno de ejecución → Ejecutar todo** (o `Ctrl + F9`)
5. ¡Los gráficos y el análisis completo se generarán automáticamente! ✅

> 💡 El notebook descarga los datos directamente desde internet. No necesitas subir ningún archivo CSV por separado.

---

### 💻 Opción 2: Ejecución Local con Jupyter

**Paso 1 — Clona el repositorio:**
```bash
git clone https://github.com/TU_USUARIO/alura-store-latam.git
cd alura-store-latam
```

**Paso 2 — Crea un entorno virtual (recomendado):**
```bash
python -m venv venv

# Windows:
venv\Scripts\activate

# Mac / Linux:
source venv/bin/activate
```

**Paso 3 — Instala las dependencias:**
```bash
pip install pandas matplotlib numpy jupyter
```

**Paso 4 — Inicia el notebook:**
```bash
jupyter notebook AluraStoreLatam.ipynb
```

**Paso 5 — Ejecuta todas las celdas:**
Menú **Cell → Run All**, o celda por celda con `Shift + Enter`.

---

### 📋 Versiones Requeridas

| Librería | Versión Mínima |
|----------|---------------|
| Python | 3.8+ |
| pandas | 1.3+ |
| matplotlib | 3.4+ |
| numpy | 1.21+ |
| jupyter | 1.0+ |

---

## 📁 Fuente de los Datos

Datos provistos oficialmente por el curso de Alura Latam:

| Archivo | Enlace directo |
|---------|----------------|
| tienda_1.csv | [⬇️ Descargar](https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_1%20.csv) |
| tienda_2.csv | [⬇️ Descargar](https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_2.csv) |
| tienda_3.csv | [⬇️ Descargar](https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_3.csv) |
| tienda_4.csv | [⬇️ Descargar](https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_4.csv) |

**Columnas disponibles en cada dataset:**
```
Producto · Categoría del Producto · Precio · Costo de envío
Fecha de Compra · Vendedor · Lugar de Compra · Calificación
Método de pago · Cantidad de cuotas · lat · lon
```

---

## 📝 Conclusión y Recomendación Final

<div align="center">

### 🏪 Se recomienda al Sr. Juan vender la **Tienda 4**

</div>

Tras el análisis de las 5 métricas, la Tienda 4 presenta el peor desempeño en **todas las dimensiones evaluadas**:

| Métrica | Resultado Tienda 4 | ¿Problema? |
|---------|--------------------|------------|
| 💰 Ingresos totales | Los más bajos de la cadena | ✅ Sí |
| 🛍️ Volumen de ventas | Inferior en casi todas las categorías | ✅ Sí |
| ⭐ Calificación promedio | La más baja (menor satisfacción) | ✅ Sí |
| 🚚 Costo de envío | Sin ventaja competitiva | ✅ Sí |
| 🏆 Ranking global | **Último lugar (4/4) en todas las métricas** | ✅ Sí |

Vender la Tienda 4 le permitirá al Sr. Juan:
- 💵 Liberar capital de un activo de **bajo rendimiento**
- 🚀 Financiar su nuevo emprendimiento con **recursos reales**
- 🎯 Concentrar la operación en las **3 tiendas más rentables**

---

## 👤 Autor

Desarrollado por **Juanito** como parte del **Challenge 1 — Data Science** de [Alura Latam](https://www.aluracursos.com/).

---

<div align="center">

*⭐ Si este proyecto te fue útil, ¡no olvides darle una estrella al repositorio!*

</div>
