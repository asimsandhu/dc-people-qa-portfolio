# DC-002 — Role-Based Access Control (RBAC) Bypass via Direct URL Entry

| Field | Value |
|---|---|
| **Bug ID** | DC-002 |
| **Severity** |  High |
| **Priority** | P1 |
| **Module** | Security / User Roles |
| **Reported By** | QA Engineering |

---

## Summary
The application relies on UI-level hiding for restricted pages rather than enforcing authorization at the routing/API layer. Users with the "External Recruiter" role can access restricted internal pages simply by typing the URL directly into their browser.

---

## Steps to Reproduce
1. Log in to the application using an account with the "External Recruiter" role.
2. Observe that restricted internal tabs/links are correctly hidden in the UI.
3. Manually type the URL of a restricted page (e.g., `/admin/client-billing`) into the browser address bar.
4. Press Enter.

## Expected Result
The system should return a `403 Forbidden` error or redirect the user back to their authorized dashboard, preventing access to the page and its underlying data.

## Actual Result
The restricted page loads successfully, displaying internal confidential data that the External Recruiter role is not authorized to view.

## Impact
**CRITICAL.** This is a severe security flaw leading to unauthorized data exposure. It compromises multi-tenant data isolation and violates standard security practices.
