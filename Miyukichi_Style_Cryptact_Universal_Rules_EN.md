# 🧠 Miyukichi-Style Cryptact Formatting Rules  
**[Complete Preservation Edition / Integrated Version + Fee-Explicit Edition] (Updated: 2025-10-21)**

---

## **Common Rules**

1. **Read numbers exactly as they appear (no rounding, ±0 deviation is prohibited).**  
   *Supplement:* Transcribe numbers exactly as seen. Only add values when instructed to. No rounding or tolerance of ±0 deviations is permitted.

2. **Skip (do not record) any row where both PnL = 0 and Fee = 0.**

3. **BONUS / LOSS entries must be arranged in chronological (ascending) order.**

4. **Output Format:** No header, tab-delimited (Excel compatible).

5. **Specify the margin currency accurately for each source.**

6. **Date and Time Format:** `YYYY/MM/DD HH:mm:ss`

---

## 💰 **GRVT Rules (USDT-based Derivatives)**

- **Source:** GRVT  
- **Base Currency (Margin):** USDT  
- **Fee Currency:** USDT  

### **Recording Policy**

1. Realized PnL **does not include fees.**  
2. The value in the Fee column shall be recorded **as a separate LOSS entry** (Fee), and **must not be combined with PnL.**  
3. If Realized PnL is positive (+): record as **BONUS (Trade Profit)**.  
   If negative (−): record as **LOSS (Trade Loss)**.  
4. If Fee is negative (−): record as **BONUS (Maker Rebate)**, using the absolute value as Quantity.  
   *Comment:* `"Maker Rebate"`  
5. If Fee is positive (> 0): record as **LOSS (Fee)**, with Quantity = Fee amount.  
   *Comment:* `"Fee"`  
6. **Funding:**  
   Positive (+) → BONUS (Funding Received)  
   Negative (−) → LOSS (Funding Payment)  
7. Skip rows where **PnL = 0 and Fee = 0.**  
8. Sort chronologically (ascending).

---

## 💵 **Pacifica Rules**

- **Source:** Pacifica  
- **Margin Currency:** USDC  
- **Realized PnL already includes fees.**  
- **Fee column is always 0.**  
- **Funding:**  
  Positive (+) → BONUS  
  Negative (−) → LOSS  
- **Maker Rebates:** Add an additional BONUS entry.  
- **Skip rows where PnL = 0 and Fee = 0.**

---

## 💎 **Hyperliquid (Hype) Rules**

- **Source:** Hyperliquid  
- **Margin Currency:** USDC  
- **Closed PnL already includes fees (final realized profit/loss).**  
- **Fee column is always 0.**  
- **Funding:**  
  Positive (+) → BONUS  
  Negative (−) → LOSS  
- **Maker Rebates:** Add an additional BONUS entry.  
- **Skip rows where PnL = 0 and Fee = 0.**

---

## 📘 **GRVT Fee Verification Checklist**  
*(Optional / Refer to separate sheet if needed)*

---

## 🧾 **Daily Aggregation Rules**

1. The user sends `"0"` to enter formatting mode.  
   → AI replies: `"Formatting mode activated."`

2. Paste the “Transaction History” from GRVT / Pacifica / Hype directly into the chat.

3. The AI will automatically perform the following:  
   - Determine **BONUS / LOSS** based on the sign of PnL.  
   - If Fee is negative (−), **add a BONUS (Rebate)** entry.  
   - If Fee is positive (> 0), **add a LOSS (Fee)** entry.  
   - Skip if both PnL = 0 and Fee = 0.

4. Finally, output the **aggregated results** for BONUS / LOSS / Rebate / Fee.  
   *Do not output intermediate calculations.*  
   Output in **Cryptact tab-delimited format.**

---

### **Output Example (GRVT / Fee-Explicit LOSS Format)**

```
2025/10/20 23:59:59	BONUS	GRVT	USDT	0.66		JPY	0	USDT	Daily BONUS Aggregation (2025-10-20)
2025/10/20 23:59:59	LOSS	GRVT	USDT	0.63		JPY	0	USDT	Daily LOSS Aggregation (2025-10-20)
2025/10/20 18:32:05	BONUS	GRVT	USDT	0.001887	JPY	0	USDT	Maker Rebate
2025/10/20 23:59:59	LOSS	GRVT	USDT	0.16011		JPY	0	USDT	Fee
```

---

## 🧩 **Checkpoints**

☑ Is a BONUS (Rebate) entry added when Fee is negative?  
☑ When Fee is positive, is the fee correctly recorded as a LOSS entry?  
☑ Are rows with both PnL and Fee equal to 0 omitted?  
☑ Are rows sorted in ascending (chronological) order?

---

## **End of Specification**
