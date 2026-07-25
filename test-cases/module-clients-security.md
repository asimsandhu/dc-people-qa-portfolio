# Test Cases — Module: Clients & Security

**Module:** Clients & RBAC  
**Author:** Asim Masood  
**Domain:** DC People Platform  

---

## TC-CLI-001: Client Creation Validation
*   **Type**: Negative Testing
*   **Steps**: 
    1. Click Add Client. 
    2. Enter invalid data types in Phone, Email, Company Phone, and Contact Phone fields. 
    3. Save.
*   **Expected Result**: Client creation is blocked with validation errors.
*   **Status**: FAILED.

## TC-CLI-002: Prevent Deletion of Active Clients
*   **Type**: Logic / Data Integrity
*   **Steps**: 
    1. Select a Client that currently has active Vacancies attached. 
    2. Attempt to delete the Client.
*   **Expected Result**: System prevents deletion, citing active dependencies (vacancies).
*   **Status**: PASSED.

## TC-SEC-001: RBAC Enforcement via Direct URL Bypass
*   **Type**: Security / Authorization
*   **Steps**: 
    1. Log in as an "External Recruiter" (restricted role). 
    2. Manually paste the URL of an admin-only or internal-only page into the browser address bar.
*   **Expected Result**: System redirects to a 403 Forbidden or Dashboard page. User cannot view restricted content.
*   **Status**: FAILED.