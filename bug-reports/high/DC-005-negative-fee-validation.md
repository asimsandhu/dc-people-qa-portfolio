# DC-005 — System Accepts Negative Values for External Recruiter Fees

| Field | Value |
|---|---|
| **Bug ID** | DC-005 |
| **Severity** | 🔴 High |
| **Priority** | P1 |
| **Module** | Vacancies / Financials |
| **Reported By** | QA Engineering |

---

## Summary
When configuring an External Recruiter Fee on a vacancy, the numerical input field lacks boundary validation. It allows users to input negative numbers, which successfully save to the database and can break downstream commission calculation logic.

---

## Steps to Reproduce
1. Navigate to the Vacancies module.
2. Click "Create Vacancy" or edit an existing one.
3. Locate the "External Recruiter Fee" input field.
4. Type a negative value (e.g., `-5000`).
5. Click Save.

## Expected Result
The form validation should block the submission, highlighting the fee field with an error message: "Fee cannot be a negative value."

## Actual Result
The vacancy saves successfully, and the database records a negative fee. 

## Impact
**HIGH.** This corrupts financial data and can lead to logic errors in billing and commission payout systems. If integrated with an external accounting API, this could cause system crashes or erroneous ledger entries.