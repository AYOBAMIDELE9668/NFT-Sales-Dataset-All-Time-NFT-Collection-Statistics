# NFT-Sales-Dataset-All-Time-NFT-Collection-Statistics
This repository provides a **comprehensive dataset** of **250 major NFT collections** and their all-time on-chain statistics, including:
- **Total Sales (in USD)**
- **Number of Unique Buyers**
- **Total Transactions**
- **Number of Unique Owners**

The dataset is designed for researchers, data scientists, NFT enthusiasts, and developers interested in exploring trends, correlations, and performance metrics across top NFT projects.

The data is **updated every 15 days** to reflect the latest market activity.

##  Dataset Structure (`nft_sales.csv`)

| Column        | Description                                  | Example Value             |
|---------------|----------------------------------------------|---------------------------|
| `Collections` | Name of the NFT collection                   | `Axie Infinity`           |
| `Sales`       | All-time sales volume in USD (formatted)     | `"$4,090,222,023"`        |
| `Buyers`      | Total unique wallet addresses that bought     | `"1,790,587"`             |
| `Txns`        | Total number of transactions                 | `"17,670,824"`            |
| `Owners`      | Total unique current holders                 | `"2,130,467"`             |

>  **Note**: All numeric fields (except collection names) are stored as **strings with commas and `$` signs** (for `Sales`). They must be cleaned before numerical analysis.
##  Key Insights (as of November 2025)

###  Top Collection by Buyers
- **Axie Infinity**: **1,790,587** unique buyers

###  Top 3 by Sales Volume
1. **Axie Infinity** – **$4.09B**  
2. **Bored Ape Yacht Club** – **$2.44B**  
3. **CryptoPunks** – **$2.39B**

###  Correlation: Buyers vs. Sales
- **Pearson correlation coefficient**: ~**0.67**  
- **Interpretation**: Strong positive relationship — collections with more unique buyers tend to generate significantly higher sales.

---

##  Suggested Analyses

- **Rank collections** by key metrics:
  - Total sales
  - Buyer-to-owner ratio
  - Transactions per buyer
- **Identify high-engagement projects**: High `Buyers` + high `Txns` (e.g., *NBA Top Shot*, *Gods Unchained*)
- **Detect whale-driven collections**: High `Sales` but low `Buyers` (e.g., *CryptoPunks*, *Bored Ape Yacht Club*)
- **Analyze ownership concentration**:  
  ```python
  df['Owner_Buyer_Ratio'] = df['Owners'] / df['Buyers']
  ## 📝 Inspiration & Use Cases

Here are some common questions and analytical prompts this dataset is designed to answer:

- **Which collection has the highest all-time buyers?**  
  → **Answer**: *Axie Infinity* with **1,790,587** unique buyers.

- **Is there a correlation between buyers and sales?**  
  → **Answer**: **Yes** — a strong positive Pearson correlation (**≈ 0.67**) indicates that collections with more unique buyers tend to generate higher total sales.

- **How much ETH (or USD) has a collection earned?**  
  → **Answer**: The `Sales` column provides **all-time sales in USD** (e.g., *Bored Ape Yacht Club*: **$2.44B**).

- **Which projects have the most active communities?**  
  → **Approach**: Combine **`Buyers`** and **`Txns`** to measure engagement.  
     - Example: *NBA Top Shot* has **446,514 buyers** and **21.8M transactions**, indicating high activity.  
     - Example: *Gods Unchained* has **65,123 buyers** and **8.97M transactions**.

- **Which collections are whale-dominated?**  
  → **Approach**: Look for **high `Sales`** but **low `Buyers`**.  
     - *CryptoPunks*: $2.39B sales from only **6,076 buyers** (~$393K avg per buyer).  
     - *Bored Ape Yacht Club*: $2.44B from **12,052 buyers**.

- **What’s the average sale price per transaction?**  
  → **Formula**: `Avg Sale Price = Sales / Txns`  
     - *Axie Infinity*: ~$231 per transaction  
     - *CryptoPunks*: ~$107,000 per transaction

- **How concentrated is ownership?**  
  → **Metric**: `Owners / Buyers` ratio  
     - Ratio **< 1**: Many buyers flipped quickly (e.g., *Mutant Ape Yacht Club*: 13K owners / 23K buyers ≈ 0.55)  
     - Ratio **> 1**: Possible duplicate ownership or multi-token holders (e.g., *Ethereum Name Service*: 487K owners / 42K buyers ≈ 11.6 → likely due to .eth domains being transferable)

This dataset is perfect for **NFT market research**, **community health analysis**, **investment due diligence**, and **data visualization projects**.
