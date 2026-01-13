# 📊 Análisis de Ventas y Optimización de Surtido – Power BI

## 🧠 Descripción del proyecto
Este proyecto presenta un análisis exploratorio y visual de datos de ventas con foco en **optimización del surtido de productos**, utilizando Power BI como herramienta principal de visualización y modelado.

El objetivo es **transformar datos transaccionales en insights accionables de negocio**, respondiendo preguntas clave como:
- ¿Qué productos generan más ingresos?
- ¿Qué tan rápido rotan los productos?
- ¿Cuáles conviene priorizar, mantener o eliminar del catálogo?

El dashboard está orientado a **toma de decisiones comerciales y de inventario**, simulando un escenario real de retail.

---

## 📁 Dataset
El dataset contiene información de ventas a nivel de línea de pedido, incluyendo:

- Identificadores de pedido, cliente y producto
- Fecha y hora de compra
- Cantidad vendida
- Precio unitario y total
- Información del producto (nombre, categoría implícita)

Los datos fueron previamente **limpiados y preparados** para su análisis.

---

## 📊 KPIs principales
El dashboard incluye indicadores clave de desempeño:

- **Ingresos Totales**
- **Unidades Totales Vendidas**
- **Pedidos Totales**
- **Productos Activos**

Estos KPIs permiten una visión rápida del rendimiento general del negocio.

---

## 📈 Visualizaciones clave

### 🔝 Top 10 productos por ingresos
Identificación de los productos con mayor aporte económico, útil para:
- Priorización de stock
- Optimización de espacio en góndola
- Foco comercial y promociones

---

### 📊 Análisis de surtido – Cuadrante 2×2 (Ingresos vs Rotación)
Se desarrolló un **análisis de cuadrantes** para clasificar productos según:

- **Eje X:** Rotación (Unidades vendidas)
- **Eje Y:** Ingresos

Los puntos de corte se definen mediante **medianas**, lo que hace el análisis robusto ante outliers.

#### Clasificación de productos:
- 🟢 **Estrella:** Alto ingreso y alta rotación  
- 🟡 **Premium:** Alto ingreso y baja rotación  
- 🔵 **Volumen:** Baja contribución económica pero alta rotación  
- 🔴 **Baja Prioridad:** Bajo ingreso y baja rotación  

Este enfoque permite:
- Detectar productos estratégicos
- Identificar oportunidades de optimización del surtido
- Reducir capital inmovilizado en inventario

---

## 🛠️ Herramientas y técnicas utilizadas
- **Power BI Desktop**
- Modelado de datos (relación Producto → Ventas)
- Medidas DAX (ingresos, unidades, medianas)
- Columnas calculadas para segmentación
- Diseño de dashboard orientado a negocio

---

## 🎯 Enfoque analítico
El proyecto prioriza:
- Claridad visual
- Métricas relevantes
- Interpretación de negocio por sobre complejidad técnica innecesaria

Está pensado como un **caso realista de análisis para retail**, aplicable a contextos de ventas, inventario y pricing.

---

## 🚀 Próximos pasos (posibles extensiones)
- Análisis temporal y estacionalidad
- Segmentación de clientes
- Integración con pronósticos de demanda
- Automatización del pipeline de datos

---

## 👤 Autor
**Matías Riffo**  
Data Analyst / Data Engineer Jr.  
📍 Argentina  

