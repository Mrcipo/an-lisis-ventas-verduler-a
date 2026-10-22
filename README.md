# Sales Analysis & Assortment Optimization — Python + Power BI

🌐 **English** · [Español](README.es.md)

![Python](https://img.shields.io/badge/Python-pandas-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green)

Exploratory and visual analysis of real sales tickets from an organic grocery store, focused on **assortment optimization**: which products to expand, keep or review.

The goal is to turn transactional data into **actionable business insights**, answering questions such as:

- Which products generate the most revenue?
- How fast does each product rotate?
- Which products should be prioritized, maintained or removed from the catalog?

## Key results

From the notebook (41 products analyzed):

- Organic products generate **72.6% of revenue** and about 65% of units and orders.
- **Class A** products (ABC analysis) concentrate 80% of revenue and units.
- **10 products** are Core Stars / class A: candidates to expand with more stock and promotion (for example, the organic banana bags).
- **1 product** is Long Tail Weak / class C: candidate to review or replace (organic red onion).
- Most remaining products are class B or premium niche: monitor and adjust prices or cross-sell.

<p align="center">
  <img src="docs/images/pareto_abc.png" alt="Pareto chart of revenue by product" width="48%">
  <img src="docs/images/top15_revenue.png" alt="Top 15 products by revenue" width="48%">
</p>
<p align="center">
  <img src="docs/images/organic_share.png" alt="Organic vs non-organic share of revenue, units and orders" width="96%">
</p>

> Chart titles and labels are in Spanish, as in the original notebook.

## Method

1. **Cleaning and preparation:** types, missing values, date features (day, month, year, weekday) and quick data-quality checks, for example `precio_total ≈ precio_unitario × cantidad`.
2. **Core assortment metrics per product:** revenue, total units, unique orders, unique customers, average price, revenue per order, monthly stability (coefficient of variation) and active months.
3. **Executive rankings:** top 15 products by revenue and by units.
4. **Pareto / ABC analysis:** class A up to 80% cumulative, B up to 95%, C the rest.
5. **2×2 segmentation (revenue vs rotation):** cut-off points are the **medians**, which makes the analysis robust to outliers.
6. **Organic vs non-organic:** an `es_organico` feature detected from the product name.
7. **Final recommendation:** a per-product table that combines ABC class, quadrant and a suggested action (expand, monitor, review).

### Segmentation

| Quadrant (notebook) | Power BI label | Revenue | Rotation |
|---|---|---|---|
| Core Stars | 🟢 Estrella | High | High |
| Nicho Premium | 🟡 Premium | High | Low |
| Traffic Builders | 🔵 Volumen | Low | High |
| Long Tail Weak | 🔴 Baja Prioridad | Low | Low |

## Power BI dashboard

`powerbi/dashboard-verduleria.pbix` contains the dashboard with:

- KPIs: total revenue, total units, total orders and active products
- Top 10 products by revenue
- 2×2 assortment quadrant (revenue vs rotation) using medians and DAX measures
- Data model Product → Sales and calculated columns for segmentation

## Data

The source data (`tickets.csv`) belongs to a real business and **is not included** in this repository. The notebook expects one row per ticket line, with the main columns `id_pedido`, `id_cliente`, `id_producto`, `nombre_producto`, `cantidad`, `precio_unitario`, `precio_total` and `fecha`.

## How to run

```bash
pip install -r requirements.txt
jupyter notebook eda_tickets.ipynb
```

Place your own `tickets.csv` next to the notebook. The rendered charts are already saved inside the notebook, so you can review the analysis without running it.

## Limitations

- No cost data, so real margins cannot be computed.
- No inventory data (stock, stock-outs, lead time).
- Monthly granularity only: no weekly seasonality or promotions.
- Limited sample of 41 products.
- Organic detection is based on the product name and may produce false positives or negatives.

## Next steps

- Add unit cost to compute gross margin.
- Add inventory data to optimize rotation and avoid stock-outs.
- Advanced time analysis: weekly seasonality and promotions.
- Customer segmentation.
- Demand forecasting.
- Validate the recommended actions with the business and measure their impact over 3–6 months.

## Author

**Matías Riffo** — Data Engineer & Backend Developer · Argentina · [GitHub](https://github.com/Mrcipo)

## License

[MIT](LICENSE)
