# FedEx Logistics Supply-Chain — Exploratory Data Analysis

An end-to-end EDA on the **SCMS Delivery History Dataset**, which tracks 10,324 shipments of HIV test kits, ARVs, and related health commodities moved across Africa and Asia on behalf of the Supply Chain Management System (SCMS) program.

## 📌 Project Overview

- **Type:** Exploratory Data Analysis (EDA)
- **Contribution:** Individual

Every day a shipment is delayed is a day a clinic somewhere is short on test kits or medication — but every dollar spent on premium freight is a dollar not spent on more product. This project digs into what actually drives **delivery delay** and **freight/insurance cost** in this network, so decisions can be made on data rather than anecdote.

## 🎯 Business Objective

Provide data-driven insights that help reduce delivery delays, choose the right shipment mode and INCO terms for a given route, and build fairer, more accurate cost and insurance models — improving delivery reliability while keeping freight spend under control.

## 🗂️ Repository Structure

```
├── FedEx_EDA_Final.ipynb          # Main analysis notebook
├── SCMS_Delivery_History_Dataset.csv   # Raw dataset
└── README.md
```

## 🛠️ Tech Stack

- **Python** — pandas, numpy
- **Visualization** — matplotlib, seaborn, plotly
- **Environment** — Jupyter Notebook

## 🔍 Analysis Pipeline

1. **Know Your Data** — shape, dtypes, duplicates, missing values. `Weight (Kilograms)` and `Freight Cost (USD)` are stored as text (placeholder strings like *"Invoiced Separately"*) and are coerced to numeric before analysis.
2. **Understanding Your Variables** — column-by-column documentation and cardinality checks.
3. **Data Wrangling** — engineers the key analytical features: `On Time` / `Late` flag, `Delivery Delay (Days)`, and `Lead Time (Days)`.
4. **Data Visualization** — 17 charts across 9 chart types (bar, horizontal bar, histogram, pie, box plot, violin plot, scatter, heatmap, time-series line), each with a *why / insight / business impact* write-up. Five charts are tagged as **Milestones**, directly answering the project's five core research questions.
5. **Solution to Business Objective** — translates findings into concrete operational recommendations.

## 📊 Key Findings

| Question | Finding |
|---|---|
| Does shipment mode affect on-time delivery? | **Air (90.4%)** on-time rate beats Ocean (82.5%); Ocean has the longest, most variable lead times |
| Do some countries see more delay? | A small number of countries — led by **Congo, DRC** — account for a disproportionate share of average delay days |
| Does lead time matter? | Short lead times correlate with more delay, especially for Ocean shipments |
| Does INCO term affect performance? | **EXW (95.0%)** on-time rate outperforms **DDP (92.0%)** |
| Does weight predict insurance cost? | Positive but imperfect correlation (**r = 0.60**) — a multi-factor model (weight + value + category) would be more accurate |

Freight cost itself is heavily right-skewed, with **Air Charter** commanding a large premium per kilogram over standard Air or Ocean freight.

## ✅ Recommendations

1. Default to **Air** for time-critical shipments; reserve **Ocean** for routes with long, reliable lead times.
2. Build **country-specific delay buffers** for the worst-performing destinations.
3. Enforce **minimum lead times by shipment mode** at the PO-creation stage.
4. Match **INCO term** to demonstrated vendor/agent logistics capability rather than a default template.
5. Move to a **multi-factor insurance pricing model** (weight + line-item value + product category).

## 🚀 Next Steps

- Build a predictive (classification) model for on-time delivery using shipment mode, country, INCO term, and lead time as features.
- Enrich the dataset with external signals (fuel prices, port congestion, political stability) to explain currently-unexplained delay variance.

