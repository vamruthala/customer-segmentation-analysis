# Customer Segmentation & Profiling

**My focus:** Customer Analytics | Tableau clustering and segment profiling

## Executive summary

I grouped **2,240 customers** into two clusters using spending across six product categories. Cluster 1 has **711 customers** with higher average annual spend and income; Cluster 2 has **1,529 customers**. I use these profiles to shape segment-specific offer tests.

## Business question and pipeline

I asked: how can I group customers by product-spending patterns and profile the segments for focused marketing decisions?

```mermaid
flowchart LR
  A[My customer category-spend analysis] --> B[Use six product-spend features]
  B --> C[Create two Tableau clusters]
  C --> D[Compare segment size and category spend]
  D --> E[Profile income, average spend, household mix]
  E --> F[Develop segment-specific offer tests]
  F --> G[Measure response before scaling]
```

## Business KPIs

| Metric | Formula / definition | Value | My interpretation |
|---|---|---:|---|
| Customers profiled | Count of customer records | **2,240** | I use this as the total customer count in the cluster profile. |
| Cluster 1 size/share | `711 ÷ 2,240`; share = cluster count ÷ total × 100 | **711 / 31.7%** | I identify Cluster 1 as the smaller segment. |
| Cluster 2 size/share | `1,529 ÷ 2,240`; share = cluster count ÷ total × 100 | **1,529 / 68.3%** | I identify Cluster 2 as the larger segment. |
| Average annual spend per customer | `Cluster annual spend ÷ customers in cluster` | C1 **$1,340**; C2 **$260** | I compare average spend per customer; C1 is about **5.15×** C2. |
| Average annual income | `Cluster income total ÷ customers in cluster` | C1 **$73K**; C2 **$42.58K** | I use income as a descriptive profile attribute, not an explanation of spending behavior. |
| Category spend | `SUM(category spend)` by cluster | C1 wine **$457.08K**, meat **$290.90K**; C2 wine **$226.76K** | I compare category contribution separately from average spend per customer. |
| Household composition | `Customers in household group ÷ cluster customers × 100` | C1: **62.3%** no children, **33.6%** one; C2: **12.8%** none, **58.1%** one, **26.0%** two, **3.1%** three | I compare household mix within each cluster. |

## Model Metrics

| Metric | Method | Value | My interpretation |
|---|---|---:|---|
| Number of clusters | Tableau clustering using six product-spend features | **2** | I profile each cluster using size, category spend, average spend, income, and household mix. |
| Predictive performance | Accuracy, precision/recall, or RMSE | Not applicable | I use unsupervised clustering, not a supervised prediction target. |

## Cluster overview

I use the spending-pattern view to compare how the two clusters behave across six product categories.

![Customer spending patterns across six category features, grouped into two clusters](assets/spending-pattern-clusters.png)

## Data exploration and assets

I explored segment size, category mix, average income, average spend, and household composition. Supporting visuals are stored in `assets/`:

- `customer-count-by-cluster.png` — compares segment sizes.
- `category-spend-by-cluster.png` — compares category totals across segments.
- `average-income-by-cluster.png` — compares reported average income.
- `average-spend-by-cluster.png` — compares average annual spend per customer.
- `children-by-cluster.png` — shows household composition by cluster.

## Insights and recommendations

- I found Cluster 1 is smaller and has higher average spend and income in the profile.
- I found Cluster 2 contains about two-thirds of the profiled customers and has lower average spend.
- I recommend testing retention or premium offers with Cluster 1 and value or category bundles with Cluster 2.
- I recommend tailoring tests to category preferences and measuring incremental spend and margin by cluster.
- I treat cluster labels as descriptive profiles and use measured campaign response to guide decisions.

## Supporting documents

- [Executive summary](docs/Executive-Summary.md)
- [Business requirements](docs/BRD-Summary.md)
- [Functional requirements](docs/FRD-Summary.md)
