# AWS Budgets — Study Notes

## 1. What is AWS Budgets?
- A cost management tool inside AWS **Billing and Cost Management**.
- Lets you set custom **cost** or **usage** thresholds and get **alerts** when actual or forecasted spend crosses them.
- Does **not** stop or limit spending by default — it only *notifies* you (unless you add "Actions").

## 2. Why it matters (especially on Free Tier)
- AWS does **not** proactively warn you when you exceed free-tier limits.
- Without a budget, the first sign of overspending is often the credit card bill.
- Free-tier accounts created after **July 15, 2025** get expiring **credits** (not the old 12-month free usage model), so tracking spend is even more important.

## 3. Types of Budgets
| Type | Purpose |
|---|---|
| Cost Budget | Track actual/forecasted $ spend against a threshold |
| Usage Budget | Track usage (e.g., hours, GB) against a threshold |
| RI Utilization Budget | Monitor Reserved Instance usage efficiency |
| RI Coverage Budget | Monitor how much usage is covered by RIs |
| Savings Plan Utilization Budget | Ensure Savings Plans are being used efficiently |
| Zero Spend Budget | Special $0 budget — alerts on ANY charge (ideal for Free Tier) |

## 4. How to Set One Up (Steps)
1. Go to **AWS Console → Billing and Cost Management → Budgets**.
2. Click **Create budget**.
3. Choose type: **Zero spend budget** (recommended for free tier) or **Cost budget** with a custom amount.
4. Set period: Monthly / Quarterly / Annual.
5. Add **alert thresholds** (e.g., 50%, 80%, 100% of budget).
6. Add your **email** as the notification recipient.
7. Review and click **Create budget**.
8. Separately, enable **Free Tier usage alerts** in Billing Preferences (a related but different feature).

## 5. Pricing — Key Distinction
- **Budgets without Actions (plain alerts):** 100% free, no limit — up to **20,000 budgets** per account.
- **Budgets with Actions (automated responses, e.g. auto-restricting IAM/resources):**
  - First **2 action-enabled budgets** are free per account.
  - Each additional one costs **$0.10/day**.
- **Budget Reports** (optional emailed summaries): **$0.01 per report**.
- Creating a budget itself never costs money — only *actions* and *reports* beyond the free quota do.

## 6. Important Notes / Gotchas
- The budget amount is **not a spending cap** — AWS keeps billing you even if you exceed it; it just alerts you.
- Each budget supports up to **5 alerts**, each alert can notify up to **10 emails** or an SNS topic.
- A **stopped** EC2 instance stops compute charges, but the attached **EBS volume** keeps billing — budgets help catch this.
- **NAT Gateways** have no free tier and bill hourly — a common surprise charge budgets can catch.
- Best practice: start broad (one account-level budget), then add specific ones per service/project as needed.

## 7. Quick Recommendation for Free Tier Beginners
- Set up **1 Zero Spend Budget** immediately after account creation.
- Add your email for alerts.
- Skip "Actions" entirely — the automated-action feature is for advanced/production use and is the only part that can cost money.
