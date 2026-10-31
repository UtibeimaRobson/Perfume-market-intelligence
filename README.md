# Perfume Market Intelligence Analysis

An end-to-end exploratory and diagnostic analysis of **1,998 perfume listings** (17 columns), covering products, pricing, sales, revenue, brands and inventory. The notebook cleans the data, identifies what drives performance, and turns the findings into practical inventory and purchasing recommendations.

**Approach:** Clean the data → Understand the market → Identify performance drivers → Examine price and sales → Translate findings into inventory actions

📓 **Notebook:** [`Perfume_Market_Intelligence_Analysis_Portfolio.ipynb`](Perfume_Market_Intelligence_Analysis_Portfolio.ipynb) (renders directly on GitHub)

---

## Business Questions

| Section | Questions |
|---|---|
| **Market Overview** | What does the product mix look like? Which price segments generate the most revenue? Which brands sell the most units? Does brand popularity relate to revenue? |
| **Market Drivers** | Which brands carry the highest inventory risk? How concentrated is revenue by country? How do men's and women's products compare, and what drives the gap? |
| **Price & Sales** | Does a higher price mean lower sales? Which price range performs best? |
| **Inventory & Action** | Where are the inventory risks and opportunities? |

## Key Findings

- **Catalogue mix:** Budget and Mid-Range products make up about 90% of listings; Luxury is about 10%.
- **Revenue by segment:** Premium generates the most revenue ($21.4M, 53.9%). Luxury has the highest prices but the lowest average revenue per product.
- **Price and sales:** Units sold fall as price rises (average units per product: Budget 839.5, Mid-Range 536.7, Luxury 124.5). The Spearman correlation between price and units sold is weak (-0.18), so price alone does not explain performance.
- **Price bands:** The $19–$30 band has the highest average revenue, but it depends on a few best-sellers (11 of the top 20). Without them it is no longer the top band, so there is no strong evidence for a single "best" price point.
- **Gender gap:** Men's and women's catalogues are almost the same size (1,000 vs 998), yet men's products generate 65.0% of revenue. Five brands (Versace, Azzaro, Davidoff, Calvin Klein, Paco Rabanne) account for 67% of the gap, and the median product performs similarly for both genders.
- **Restock risk:** 414 products (20.7% of the catalogue) are fast-selling but low in stock, and they account for 47.9% of revenue; 241 of them are at zero stock. This is revenue already generated, not revenue currently at risk.
- **Slow-moving stock:** About $279K in retail-value stock sits in slow-moving products (41 high-stock and 343 medium-stock products).
- **Geographic caveat:** The United States accounts for about 99% of revenue, so country-level comparisons should be treated carefully.

## Data Cleaning Highlights

- Recovered 2 missing brand names from product titles.
- Standardised brand names: **401 raw values reduced to 319 distinct brands**, merging only clear misspellings and alternate names.
- Recovered 48 further brands from product titles, only where exactly one known brand matched; 109 rows remain `UNKNOWN`.
- Standardised country names (`Estados Unidos` → `United States`) and product-type labels (`Eau De Toilette` → `EDT`).

## Data

The analysis uses `Perfume_Market_Intelligence_Dataset.csv` (1,998 rows × 17 columns), located in the `data/` folder.

- **Source:** Kaggle, "Global Perfume E-Commerce Analytics Dataset" by Muhammad Zohair Baloch: https://www.kaggle.com/datasets/zohairbaloch/global-perfume-e-commerce-analytics-dataset
- **Licence / usage notes:** "Other (specified in description)" on Kaggle. The dataset is not included in this repository; download it from the link above and save it as `data/Perfume_Market_Intelligence_Dataset.csv` before running the notebook.
Key columns include `Brand`, `Product`, `Gender`, `Product_Type`, `Price`, `Sold`, `Available`, `Revenue`, `Price_Category`, `Market_Segment`, `Sales_Performance`, `Brand_Popularity`, `Inventory_Status`, `Stock_Turnover` and `Country`. A full column guide is inside the notebook.

## Limitations

- Conclusions are based only on the information in the dataset. Where the data cannot confirm a business decision, the finding is flagged for further investigation.
- The dataset cannot distinguish a sold-out product from a discontinued one.
- Stock value is estimated at retail price (`Available × Price`), not purchase cost.

## How to Run

**1. Get the code**

```bash
git clone https://github.com/UtibeimaRobson/perfume-market-intelligence.git
cd perfume-market-intelligence
```

No git? Click the green **Code** button on this page, choose **Download ZIP**, and unzip it.

**2. Get the dataset**

The dataset is not included in this repository. Download it from [Kaggle](https://www.kaggle.com/datasets/zohairbaloch/global-perfume-e-commerce-analytics-dataset), create a folder called `data` in the project folder, and save the file there as `Perfume_Market_Intelligence_Dataset.csv`.

**3. Install the libraries** (Python 3.10 or newer)

```bash
pip install -r requirements.txt
```

**4. Open the notebook**

```bash
jupyter notebook Perfume_Market_Intelligence_Analysis_Portfolio.ipynb
```

Run the notebook from the project folder so the data path resolves, then use **Kernel → Restart & Run All** to reproduce every result.
```

Run the notebook from the repository root so the dataset path resolves correctly.

## Repository Structure

```
├── README.md
├── requirements.txt
└── Perfume_Market_Intelligence_Analysis_Portfolio.ipynb
```

## Tools

Python · pandas · matplotlib · seaborn · Jupyter

## Author

**Utibeima Robson** — freelance data analyst (Excel,SQL, Power BI, Python, data cleaning, dashboards and reporting)

utibeimarobson18@gmail.com
