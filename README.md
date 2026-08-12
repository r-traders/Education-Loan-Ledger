# Education Loan Ledger

A personal, browser-based tool to track an education loan with phased disbursements, plan adhoc payments, manage related investments, and project payoff timelines. All data stays in your browser — no server, no signup, no cloud.

## Files in this folder

- **`index.html`** — the interactive tracker tool
- **`README.md`** — this file

## What it does

- Track outstanding balance with current interest rate
- Plan EMI step-ups at each disbursement so you stay ahead of interest
- Log actual payments (regular + adhoc) and compare to the plan
- Track future disbursements
- Track investment corpus for funding adhoc payments and Phase 2 EMI cushion
- Project month-by-month loan trajectory through full payoff
- Compare scenarios

## Quick start (host on GitHub Pages)

1. Create a new GitHub repository (e.g., `loan-ledger`)
2. Upload `index.html` to the repo root
3. Go to **Settings → Pages**
4. Under **Source**, select branch `main` and folder `/ (root)`
5. Click **Save**. Live at `https://<your-username>.github.io/loan-ledger/` in ~1 minute

## Default setup (May 2026)

| Field | Default |
|---|---|
| Outstanding balance | ₹47,15,469 |
| Interest rate | 7.35% |
| Statement date | May 2026 |
| Moratorium ends | December 2029 |
| Phase 2 EMI | ₹1,00,000 |
| Surplus buffer | ₹1,000 |
| Annual adhoc | ₹1,00,000 (in March, 3 years) |
| Disbursements | Sep 26 ₹12L, Jan 27 ₹12L, May 27 ₹6.5L, Sep 27 ₹12L |

## EMI step-up schedule

After each disbursement, EMI rises to keep ahead of new interest level:

| Phase | Recommended EMI |
|---|---|
| Now (May 2026) | ₹30,000 |
| Sep 2026 (after ₹12L) | ₹37,000 |
| Jan 2027 (after ₹12L) | ₹44,500 |
| May 2027 (after ₹6.5L) | ₹47,500 |
| Sep 2027 (after final ₹12L) | ₹55,000 |
| Jan 2030 (Phase 2 begins) | ₹1,00,000 |

## Investment plan

Two pots, each with a specific job:

### Pot 1: Adhoc Fund (₹1L lumpsum + ₹5k/month)

- **Fund:** HDFC Liquid Fund — Direct — Growth
- **Purpose:** Fund ₹1L adhoc payment each March (2027, 2028, 2029)
- **Risk:** Very low
- **Expected return:** ~6.5%

### Pot 2: Long-term Cushion (₹3,500/month)

- **Fund:** ICICI Prudential Dividend Yield Equity Fund — Direct — Growth
- **Purpose:** Build corpus for one-time prepayment when Phase 2 starts (Jan 2030), or buffer through Phase 2
- **Risk:** Moderate (defensive equity)
- **Expected return:** ~14% long-term average

**Why dividend yield over Nifty 50:** Lower volatility, defensive in downturns, consistent 14-17% historical returns. Better suited for conservative long-term investors.

**Total monthly investment outflow: ₹8,500**

## Setting up the SIPs

Use any of: **Groww**, **Zerodha Coin**, **MFCentral**, or direct AMC websites.

For each fund:
1. Search the fund name exactly
2. **Always select Direct plan** (NOT Regular) — saves ~0.5%/year
3. **Always select Growth option** (NOT IDCW/Dividend) — for compounding
4. Set up auto-debit, pick date 2-3 days after salary credit

## Backing up data

Click **Export Data** to download a JSON file. Save in cloud storage (Drive/Dropbox). Use **Import** to restore.

## Important disclaimers

### Tax

- **Section 80E**: Interest paid on education loan is fully tax-deductible for up to 8 years from when EMI repayment officially begins (OLD tax regime only). Available to the person legally repaying the loan (borrower or co-borrower). Confirm your status with the bank.
- **Liquid fund**: Returns taxed at your slab rate
- **Equity fund**: 12.5% LTCG above ₹1.25L/year if held >1 year; 20% STCG if held <1 year

### Investment caveats

- **Past performance does not guarantee future returns**. Equity is volatile short term.
- **Don't put adhoc money in equity or commodities** — they can fall 20-30% when you need the money most.
- These suggestions are **general framework reasoning, not SEBI-registered financial advice**. For specific suitability, consult a fee-only advisor.

### Math caveats

- Uses monthly compounding (close to bank's daily method)
- Investment returns are long-term historical averages, not guarantees
- Floating loan rate may change with RBI repo movements

## Tech

Single HTML file, vanilla JavaScript, localStorage. No build step, no dependencies.

Built May 2026.
