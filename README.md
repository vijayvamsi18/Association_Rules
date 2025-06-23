# 🛒 Market Basket Analysis using Association Rule Mining

This project implements **Association Rule Mining** on a transactional dataset using the **Apriori Algorithm** to uncover interesting relationships between items purchased together. It helps identify frequent itemsets and generate rules using support, confidence, and lift metrics.

## 📂 Dataset

The dataset used is `Online_retail.csv`, where each row represents a transaction — a list of items bought together.

Example:
```
shrimp,almonds,avocado,vegetables mix,green grapes
```

## 📌 Objectives

- Perform **data preprocessing** on transaction data.
- Use **Apriori algorithm** to generate frequent itemsets.
- Derive **association rules** from these itemsets.
- Analyze rules based on **support**, **confidence**, and **lift**.
- Visualize the frequent patterns and rules.

## ⚙️ Technologies Used

- Python 🐍
- Pandas
- Mlxtend (for Apriori & association_rules)
- Jupyter Notebook

## 🧪 How It Works

1. **Data Loading & Preprocessing**:
   - Load data using `pandas`.
   - Split transaction strings into item lists.

2. **Transaction Encoding**:
   - Use `TransactionEncoder` to convert transactions into a binary format.

3. **Frequent Itemsets Mining**:
   - Use `mlxtend.frequent_patterns.apriori()` to find frequent itemsets with a minimum support threshold.

4. **Generating Association Rules**:
   - Use `association_rules()` function to generate rules based on confidence and lift thresholds.

5. **Rule Evaluation**:
   - Filter top rules and sort by metrics (lift/confidence).

## 📊 Results

- Discovered various combinations of items that frequently appear together.
- Generated strong association rules like:
  ```
  {milk, bread} → {butter} with confidence = 0.75 and lift = 2.5
  ```
- Rules were filtered and visualized for better insights.

## ✅ Example Output

```python
frequent_itemsets = apriori(df, min_support=0.02, use_colnames=True)
rules = association_rules(frequent_itemsets, metric="lift", min_threshold=1)
rules.sort_values('lift', ascending=False).head()
```

## 🚀 How to Run

1. Clone the repository or open the notebook:
   ```
   git clone <your-repo-url>
   ```
2. Open `Association_rules.ipynb` in Jupyter Notebook.
3. Run all cells to execute the full pipeline.

## 📎 Dependencies

Install with:
```bash
pip install pandas mlxtend
```

## 📌 Conclusion

This project demonstrates how Association Rule Mining can uncover hidden patterns in transaction data and assist in business decisions like product placement, bundling, and recommendations.
