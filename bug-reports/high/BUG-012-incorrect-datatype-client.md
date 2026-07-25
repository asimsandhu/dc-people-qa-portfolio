# BUG-012 — Client Creation Form Accepts Incorrect Data Types

| Field | Value |
|---|---|
| **Bug ID** | BUG-012 |
| **Severity** | 🔴 High |
| **Priority** | P2 |
| **Module** | Clients / CRM |
| **Reported By** | QA Engineering |

---

## Summary
The "Add Client" and "Edit Client" forms lack fundamental data type validation. Fields specifically intended for numeric data (like Phone Number and Company Phone) accept alphabetic characters, and email fields accept strings without the `@` symbol.

---

## Steps to Reproduce
1. Navigate to the Clients module.
2. Click "Add Client".
3. In the "Phone" and "Contact Phone" fields, enter alphabetic characters (e.g., `abcXYZ`).
4. In the "Email" field, enter a string without domain formatting (e.g., `notanemail`).
5. Click Save.

## Expected Result
Form submission should be blocked. The UI should display standard validation errors ("Please enter a valid phone number", "Please enter a valid email address").

## Actual Result
The client profile is created successfully, storing corrupted and unusable contact data in the CRM database.

## Impact
**HIGH.** Direct impact on data integrity. Invalid contact numbers prevent the platform's communication features from functioning and require manual database cleanup.