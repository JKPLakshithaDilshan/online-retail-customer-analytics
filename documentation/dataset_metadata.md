# Dataset Metadata and Provenance

## Dataset Identification

* Dataset name: Online Retail
* Local filename: `Online_Retail.xlsx`
* Local path: `data/raw/Online_Retail.xlsx`
* Source: UCI Machine Learning Repository
* Dataset page: https://archive.ics.uci.edu/dataset/352/online+retail
* DOI: https://doi.org/10.24432/C5BW33
* Dataset creator: Daqing Chen
* Donated to UCI: 5 November 2015
* License: Creative Commons Attribution 4.0 International
* File size: Approximately 23 MB
* Number of rows: 541,909
* Number of columns: 8
* Transaction period: 01 December 2010 to 09 December 2011

## Dataset Fingerprint

* Algorithm: SHA-256
* SHA-256 value:

```text
43465a06f2ccf7c8b5bd2892bc7defb52f97487934fe93b16ae4c3936424676d
```

* Verification command on macOS:

```bash
shasum -a 256 data/raw/Online_Retail.xlsx
```

Every group member must obtain the same SHA-256 value before conducting the analysis. A different value may indicate a different or modified dataset file.

## Dataset Description

The dataset contains transaction-level records from a UK-based, non-store online retailer that mainly sells unique all-occasion gifts. Many of the retailer's customers are wholesalers.

Each row represents one product line within an invoice. Therefore, a single invoice can appear across multiple rows when multiple products were purchased.

## Variables

| Variable    | Description                                                             | Data Role              |
| ----------- | ----------------------------------------------------------------------- | ---------------------- |
| InvoiceNo   | Invoice identifier; a value beginning with `C` indicates a cancellation | Basket identifier      |
| StockCode   | Unique product identifier                                               | Item identifier        |
| Description | Product description                                                     | Product interpretation |
| Quantity    | Quantity of the product recorded in the transaction                     | Transaction measure    |
| InvoiceDate | Date and time of the transaction                                        | Temporal variable      |
| UnitPrice   | Product price per unit in pounds sterling                               | Monetary measure       |
| CustomerID  | Unique customer identifier                                              | Customer grouping key  |
| Country     | Customer's country                                                      | Geographic variable    |

## Planned Units of Analysis

### Customer Segmentation

One row in the engineered feature dataset will represent one identified customer.

### Association-Rule Mining

One basket will represent one valid purchase invoice containing one or more products.

### Segment-Specific Association Analysis

Each valid purchase invoice will be connected to the final segment assigned to its identified customer.

## Data Handling Rules

* The original Excel file must remain unchanged.
* The raw dataset is excluded from Git tracking.
* Derived datasets must be saved inside `data/processed/`.
* Data-cleaning decisions must be recorded in `decision_log.csv`.
* Before-and-after row counts must be reported for each cleaning decision.
* Cancelled and returned transactions must be separated before purchase-only analysis.
* Rows without a valid CustomerID cannot be assigned to customer segments.
* Outliers must be investigated before removal, transformation, or capping.

## Initial Limitations

* The dataset covers approximately one year.
* December 2011 is incomplete because records end on 09 December 2011.
* The data represents one UK-based retailer.
* Many customers may be wholesalers, which could create extreme purchasing patterns.
* Customer demographic information is unavailable.
* Recency can indicate inactivity but cannot prove that a customer has churned.
* Product associations do not establish causal relationships.

## Citation

Chen, D. (2015). Online Retail [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33
