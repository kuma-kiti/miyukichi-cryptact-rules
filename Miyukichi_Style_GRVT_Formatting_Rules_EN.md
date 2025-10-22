# 🧠 Miyukichi-Style GRVT Formatting Rules
*(Extended & Preserved Edition – October 2025)*

---

## **Basic Specifications**
- **Source:** GRVT  
- **Base Currency:** USDT  
- **Fee Currency:** USDT  
- **Format:** No header, Tab-delimited (Excel compatible)  
- **Sort Order:** Ascending (Chronological order)

---

## **Recording Rules**

### ① Profit (Realized PnL > 0)
- **Type:** BONUS  
- **Quantity:** Profit amount  
- **Fee:** 0  
- **Comment:** “決済利益 (銘柄名 Long/Short)”

### ② Loss (Realized PnL < 0)
- **Type:** LOSS  
- **Quantity:** Absolute value of loss  
- **Fee:** 0  
- **Comment:** “決済損失 (銘柄名 Long/Short)”

### ③ Negative Fee (Maker Rebate)
- **Type:** BONUS  
- **Quantity:** Absolute value of rebate  
- **Fee:** 0  
- **Comment:** “メイカーリベート”

### ④ When Both PnL and Fee Exist
- Classify according to the **sign of PnL** (BONUS for positive / LOSS for negative).  
- Record the **Fee amount as-is** in the Quantity field.  
- **Comment:** “決済利益” or “決済損失 (銘柄名)”

### ⑤ Funding (Interest / Swap)
- Record Funding **PnL in the Quantity field.**  
- **Comment:** “Funding Payment” or “Funding Received”  
- **Negative → LOSS / Positive → BONUS**

---

## **Aggregation Rules (Miyukichi Standard – Article 4 Extended Specification)**
For daily or period-end summaries, always create the following **6 categories**:  
(*Note: Separate trading PnL and funding PnL clearly into distinct categories.*)

| Category | Type | Quantity Field | Fee Field | Comment |
|-----------|------|----------------|------------|----------|
| 1 | BONUS | 決済利益 | 0 | 日次 決済利益集計 (YYYY-MM-DD) |
| 2 | LOSS | 決済損失 | 0 | 日次 決済損失集計 (YYYY-MM-DD) |
| 3 | BONUS | 受取 ファンディング | 0 | 日次 Funding Received 集計 (YYYY-MM-DD) |
| 4 | LOSS | 支払 ファンディング | 0 | 日次 Funding Payment 集計 (YYYY-MM-DD) |
| 5 | BONUS | メイカーリベート合計 | 0 | メイカーリベート 集計 (YYYY-MM-DD) |
| 6 | LOSS | 手数料合計 | 0 | 手数料 集計 (YYYY-MM-DD) |

---

## 💬 **Notes**
- **Category Output:**  
  You do **not** need to output all six categories — omit any that have no values.  
- **Realized PnL:**  
  Represents only confirmed profits or losses from trade entries and closes.  
- **Funding PnL:**  
  Represents interest or swap-related earnings/losses from open positions.  
- **Rebates and Fees:**  
  Are recorded **independently** as before.  
- **Quantity Field:** Always contains the **exact monetary value (e.g., USDC/USDT)**.  
- **Fee Field:** Always **0**.  
  → This ensures a clean Cryptact-compatible tab-delimited export consisting of 4 rows (BONUS / LOSS / Rebate / Fee).  
- **Zero values:** Rows with a Quantity of 0 are **cut (omitted)** automatically.

---

## 🧾 **Example Output**
```
2025/10/22 23:59:59	BONUS	GRVT	USDT	1.0600000000	0	日次 決済利益集計 (2025-10-22)
2025/10/22 23:59:59	LOSS	GRVT	USDT	0.5300000000	0	日次 決済損失集計 (2025-10-22)
2025/10/22 23:59:59	BONUS	GRVT	USDT	0.0039930000	0	メイカーリベート 集計 (2025-10-22)
2025/10/22 23:59:59	LOSS	GRVT	USDT	0.2806020000	0	手数料 集計 (2025-10-22)
```

---

## 🧩 **Editable Notes**
- You may update or append new sections in Markdown syntax.  
- Maintain Japanese labels for output consistency.  
- Keep tab spacing intact for Excel/Cryptact compatibility.  
- Use version control if shared between AI models.

---
