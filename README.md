# Education Loan Ledger

A personal, browser-based tool to track an education loan with phased disbursements, plan adhoc payments, and project payoff timelines. All data stays in your browser (localStorage) — no server, no signup, no cloud.

## What it does

- **Track outstanding balance** with current interest rate
- **Plan EMI step-ups** at each disbursement so you stay ahead of interest
- **Log actual payments** (regular + adhoc) and compare to the plan
- **Track future disbursements** (semester fees, etc.)
- **Track investment corpus** for funding adhoc payments and Phase 2 EMI cushion
- **Project month-by-month** loan trajectory through full payoff
- **Compare scenarios** to see impact of different EMI / adhoc / buffer levels

## Quick start (host on GitHub Pages)

1. Create a new GitHub repository (e.g., `loan-ledger`).
2. Upload `index.html` to the repo root.
3. Go to **Settings → Pages**.
4. Under **Source**, select branch `main` and folder `/ (root)`.
5. Click **Save**. Your tool is live at `https://<your-username>.github.io/loan-ledger/`.
6. Bookmark the URL on your phone and laptop.

That's it. No build step, no dependencies.

## Default setup (May 2026)

The tool comes pre-loaded with the following starting values — edit them on the **Setup** tab:

| Field | Default |
|---|---|
| Outstanding balance | ₹47,15,469 |
| Interest rate | 7.35% |
| Statement date | May 2026 |
| Moratorium ends | December 2029 |
| Phase 2 EMI | ₹1,00,000 |
| Surplus buffer per EMI | ₹2,000 |
| Annual adhoc | ₹1,00,000 |
| Adhoc month | March |
| Adhoc years | 3 |
| Disbursements | Sep 26 ₹12L, Jan 27 ₹12L, May 27 ₹6.5L, Sep 27 ₹12L |

## How the EMI step-up logic works

After each disbursement, the tool recalculates monthly interest at the new balance and recommends EMI = (interest + buffer), rounded to nearest ₹500.

Example with ₹2,000 buffer:
- Balance ₹47.15L → interest ₹28,882 → recommended EMI **₹30,000**
- After Sep 2026 disbursement, balance ₹59.4L → interest ₹36,381 → recommended EMI **₹38,500**
- After Jan 2027 disbursement, balance ₹71.3L → interest ₹43,673 → recommended EMI **₹45,500**
- After May 2027 disbursement, balance ₹77.7L → interest ₹47,602 → recommended EMI **₹49,500**
- After Sep 2027 disbursement (final), balance ₹89.6L → interest ₹54,898 → recommended EMI **₹57,000**

This keeps the balance from drifting upward during moratorium.

## Investment tracker

Two pots:

1. **Adhoc Fund** (short-term, debt/liquid fund) — funds the ₹1L/year adhoc withdrawals
2. **Long-term Cushion** (equity) — builds a one-time prepayment corpus by Phase 2 start

Default suggestion: ₹1L lumpsum + ₹5k/month into liquid fund, ₹3k/month into equity index fund.

## Backing up your data

Use **Export Data** to download a JSON file. Keep this in cloud storage (Drive / Dropbox) as backup. Use **Import** to restore on a different device or browser.

## Notes & disclaimers

- This is a **personal planning tool**, not regulated financial advice
- Interest math uses monthly compounding (close to bank's daily method, slight variance possible)
- Investment return assumptions are rough estimates — actual returns vary
- Tax calculations (80E etc.) are not included — consult a tax professional
- For Section 80E claim, the borrower or co-borrower paying the loan can deduct interest paid for up to 8 assessment years from when repayment starts (old tax regime only)

## Tech

- Single HTML file, no build step
- Vanilla JS, no frameworks
- localStorage for data persistence
- Self-hosted typography via Google Fonts (Fraunces + Inter + JetBrains Mono)

Built May 2026. Designed for the patient task of paying down a loan over 14 years.
