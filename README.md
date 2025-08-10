# Market Basket Analysis: UK Online Retail Data 🛒
## Project Overview
This project conducts a comprehensive Market Basket Analysis (MBA) on a real-world transactional dataset from a UK-based online retail store. The goal is to uncover hidden purchasing patterns and strong associations between products, providing actionable insights to enhance sales strategies, optimize product placement, and improve marketing efforts.

## Methodology 
The analysis followed a structured machine learning pipeline:
1.  **Data Acquisition & Filtering:** Loaded and focused on UK-specific sales data.
2.  **Data Cleaning:** Handled missing values, removed canceled orders, and cleaned product descriptions.
3.  **Transaction Sampling:** Applied a 20% transaction sample for efficient processing.
4.  **One-Hot Encoding:** Transformed transactional data into a suitable format for association rule mining.
5.  **Apriori Algorithm:** Identified frequent itemsets (groups of products frequently bought together) with a minimum support of 0.01.
6.  **Association Rule Generation:** Derived "if-then" rules from frequent itemsets, evaluated using **Confidence** (reliability) and **Lift** (strength of association beyond chance). Rules with `confidence > 0.7` and `lift > 1.2` were filtered.

## Key Findings: Frequent Items 
| Antecedent(s) | Consequent(s) | Confidence | Lift | Recommendation |
| :--- | :--- | :--- | :--- | :--- |
| BEADED CRYSTAL HEART GREEN ON STICK | BEADED CRYSTAL HEART PINK ON STICK | 0.88 | 58.27 | **Co-locate** green & pink beaded hearts for cross-selling. |
| BEADED CRYSTAL HEART GREEN ON STICK, DOTCOM POSTAGE | BEADED CRYSTAL HEART PINK ON STICK | 0.88 | 58.27 | **Bundle** green heart & postage; customers likely buy pink heart too. |
| POPPY'S PLAYHOUSE BATHROOM, POPPY'S PLAYHOUSE KITCHEN | POPPY'S PLAYHOUSE BEDROOM, POPPY'S PLAYHOUSE LIVINGROOM | 0.93 | 58.13 | **Bundle** Bathroom & Kitchen; customers likely buy Bedroom & Livingroom. |
| REGENCY SUGAR BOWL GREEN | REGENCY MILK JUG PINK, REGENCY TEAPOT ROSES | 0.72 | 57.96 | **Co-locate** green sugar bowl with pink milk jug & roses teapot. |
| REGENCY MILK JUG PINK, REGENCY TEAPOT ROSES | REGENCY SUGAR BOWL GREEN | 0.84 | 57.96 | **Bundle** pink milk jug & roses teapot; customers likely buy green sugar bowl. |
| POPPY'S PLAYHOUSE BEDROOM, POPPY'S PLAYHOUSE BATHROOM | POPPY'S PLAYHOUSE KITCHEN, POPPY'S PLAYHOUSE LIVINGROOM | 0.90 | 57.75 | **Bundle** Bedroom & Bathroom; customers likely buy Kitchen & Livingroom. |
| POPPY'S PLAYHOUSE BEDROOM, POPPY'S PLAYHOUSE KITCHEN, POPPY'S PLAYHOUSE LIVINGROOM | POPPY'S PLAYHOUSE BATHROOM | 0.72 | 55.50 | **Bundle** Bedroom, Kitchen, Livingroom; customers likely buy Bathroom. |
| POPPY'S PLAYHOUSE BATHROOM | POPPY'S PLAYHOUSE BEDROOM, POPPY'S PLAYHOUSE KITCHEN, POPPY'S PLAYHOUSE LIVINGROOM | 0.81 | 55.50 | **Co-locate** Bathroom with Bedroom, Kitchen, Livingroom sets. |
| REGENCY SUGAR BOWL GREEN, REGENCY TEAPOT ROSES | REGENCY MILK JUG PINK | 0.90 | 53.09 | **Bundle** green sugar bowl & roses teapot; customers likely buy pink milk jug. |
| POPPY'S PLAYHOUSE BATHROOM | POPPY'S PLAYHOUSE KITCHEN, POPPY'S PLAYHOUSE LIVINGROOM | 0.83 | 52.96 | **Co-locate** Bathroom with Kitchen & Livingroom sets. |
| REGENCY TEA PLATE ROSES, REGENCY TEA PLATE GREEN | REGENCY TEA PLATE PINK | 0.78 | 52.77 | **Bundle** Roses & Green tea plates; customers likely buy Pink tea plate. |
| REGENCY TEA PLATE PINK | REGENCY TEA PLATE ROSES, REGENCY TEA PLATE GREEN | 0.87 | 52.77 | **Co-locate** Pink tea plate with Roses & Green tea plates. |
| POPPY'S PLAYHOUSE BATHROOM | POPPY'S PLAYHOUSE BEDROOM, POPPY'S PLAYHOUSE LIVINGROOM | 0.83 | 52.05 | **Co-locate** Bathroom with Bedroom & Livingroom sets. |
| POPPY'S PLAYHOUSE BATHROOM, POPPY'S PLAYHOUSE KITCHEN | POPPY'S PLAYHOUSE LIVINGROOM | 0.95 | 50.89 | **Bundle** Bathroom & Kitchen; customers likely buy Livingroom set. |
| POPPY'S PLAYHOUSE BEDROOM, POPPY'S PLAYHOUSE BATHROOM, POPPY'S PLAYHOUSE KITCHEN | POPPY'S PLAYHOUSE LIVINGROOM | 0.95 | 50.83 | **Bundle** Bedroom, Bathroom, Kitchen; customers likely buy Livingroom set. |
| BLUE POLKADOT CUP | PINK POLKADOT CUP | 0.75 | 49.92 | **Co-locate** Blue Polkadot Cup with Pink Polkadot Cup. |
| PINK POLKADOT CUP | BLUE POLKADOT CUP | 0.73 | 49.92 | **Co-locate** Pink Polkadot Cup with Blue Polkadot Cup. |
| REGENCY MILK JUG PINK | REGENCY SUGAR BOWL GREEN | 0.73 | 49.82 | **Co-locate** Pink Regency Milk Jug with Green Regency Sugar Bowl. |
| REGENCY SUGAR BOWL GREEN | REGENCY MILK JUG PINK | 0.85 | 49.82 | **Co-locate** Green Regency Sugar Bowl with Pink Regency Milk Jug. |


## Actionable Recommendations & Business Impact 
The derived association rules provide concrete strategies for sales optimization:
* **Strategic Product Placement:** Co-locating highly associated items (e.g., "Beaded Crystal Hearts" of different colors, "Poppy's Playhouse" sets) in-store and optimizing their online display.
* **Bundling & Promotions:** Creating attractive product bundles (e.g., "Regency Tea Set" components) and implementing "buy one, get X% off another" offers for items with strong correlations.
* **Targeted Marketing:** Leveraging these rules for personalized recommendations in emails or website suggestions to increase customer basket size.



## Technologies Used 
* Python
* Pandas (for data manipulation)
* `mlxtend` (for Apriori and Association Rules)
* Matplotlib / Seaborn (for optional visualizations)
