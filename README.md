<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&pause=1000&color=0EA5E9&center=true&vCenter=true&width=800&lines=QA+Engineering+Portfolio;DC+People+HR+%26+Recruitment+Platform;Manual+Testing+%7C+Test+Design+%7C+Defect+Tracking" alt="QA Portfolio" />

# 🏢 DC People — Enterprise HR & Recruitment Platform QA

### Comprehensive Quality Assurance Portfolio for an Enterprise B2B Application

[![QA Engineer](https://img.shields.io/badge/Role-QA%20Engineer-0EA5E9?style=for-the-badge&logo=checkmarx&logoColor=white)]()
[![Domain](https://img.shields.io/badge/Domain-HR%20%2F%20Recruitment-purple?style=for-the-badge&logo=target&logoColor=white)]()
[![Testing Type](https://img.shields.io/badge/Testing-Manual%20%26%20Functional-F59E0B?style=for-the-badge&logo=testinglibrary&logoColor=white)]()
[![Test Cases](https://img.shields.io/badge/Test%20Cases-Authored-10B981?style=for-the-badge)]()

[📋 Bug Reports](#-bug-reports) · [✅ Test Cases](#-test-cases) · [🎯 Project Scope](#-project-overview) · [🛠 Methodology](#-testing-methodology)

</div>

---

## 👤 About This Portfolio

> This portfolio showcases my QA Engineering work on **DC People**, a private enterprise web application used by HR departments, recruiters, and corporate brokers to source, manage, and match candidates with job vacancies.
>
> The documentation below highlights my ability to break down complex business requirements into structured test cases, identify critical edge-case defects in data processing (like CV parsing and LinkedIn scraping), and write professional, actionable bug reports for the engineering team.

---

## 🧠 Project Overview — "DC People"

| Aspect | Details |
|---|---|
| **Application Domain** | Human Resources, Recruitment, Broker Management |
| **Target Audience** | Internal HR, External Recruiters, Corporate Brokers |
| **Core Modules Tested** | `Candidates`, `Clients`, `Vacancies`, `AI Matcher`, `Role-Based Access Control (RBAC)` |
| **Key Functionality** | Bulk CV parsing, LinkedIn data scraping, AI-assisted job matching, multi-tenant data isolation |

---

## 📊 Testing Highlights & Discoveries

During the testing lifecycle, I focused heavily on data integrity and edge-case handling. Key findings included:

*   **Security / Access Control**: Discovered privilege escalation flaws where External Recruiters could access restricted pages via direct URL manipulation.
*   **Data Validation Flaws**: Identified critical failures where negative fees were accepted in financial fields, and alphabetic characters bypassed phone number validations.
*   **Integration Defects**: Uncovered workflow blockers in the LinkedIn import scraper and CV parsing engines (PDF image handling failures).

---

## 🗂️ Repository Structure

```
dc-people-qa-portfolio/
│
├── 📁 bug-reports/
│   ├── high/                   # Business-blocking or data integrity bugs
│   ├── medium/                 # Functional issues with workarounds
│   └── low/                    # Minor validation or UI issues
│
├── 📁 test-cases/
│   ├── module-candidates.md    # CV uploads, parsing, editing
│   ├── module-clients.md       # CRM functionality
│   ├── module-vacancies.md     # Job creation, AI matching
│   └── module-security.md      # RBAC and role testing
│
└── README.md
```

---

## 🐛 Bug Reports (Key Discoveries)

The following are detailed reports of critical defects I discovered during testing. Full reports are available in the [`/bug-reports`](./bug-reports/) directory.

### 🔴 High Severity (P1)

| Bug ID | Title | Module | Impact |
|---|---|---|---|
| [DC-002](./bug-reports/high/DC-002-rbac-url-bypass.md) | External Recruiter can bypass RBAC via direct URL entry | Security / Roles | Unauthorized access to internal confidential data |
| [DC-005](./bug-reports/high/DC-005-negative-fee-validation.md) | System accepts negative numerical values for External Recruiter Fees | Vacancies | Financial calculation errors in broker commissions |
| [DC-001](./bug-reports/high/DC-001-docx-preview-download-error.md) | Bulk uploaded DOCX CVs force download instead of in-browser preview | Candidates | Breaks recruiter UX workflow, forcing local file management |
| [BUG-012](./bug-reports/high/BUG-012-incorrect-datatype-client.md) | Client creation bypasses data type validation on phone/email fields | Clients | Corrupts CRM database with malformed contact data |

### 🟠 Medium Severity (P2)

| Bug ID | Title | Module | Impact |
|---|---|---|---|
| [DC-003](./bug-reports/medium/DC-003-pdf-image-upload-crash.md) | PDF files containing specific image formats fail to upload | Candidates | Prevents candidates with graphic CVs from being parsed |
| [DC-004](./bug-reports/medium/DC-004-scraper-modal-freeze.md) | LinkedIn scraping modal remains stuck open after successful import | Candidates | UI friction requiring manual page refresh |

---

## ✅ Test Case Design

I designed comprehensive test suites focusing on both positive workflows and negative edge cases. Full suites are in the [`/test-cases`](./test-cases/) directory.

### Module: Candidates & CV Management
*   **Bulk Upload Constraints**: Testing limits (>10 files), invalid formats (.exe, .jpg), and valid multi-format batches (.pdf, .docx).
*   **Data Scrape Import**: Validating LinkedIn URL parsing, timeout handling, and data mapping to internal database fields.
*   **Data Integrity**: Attempting to inject alphabets into numeric fields (phone) and future dates into past-event trackers (contact history).

### Module: Vacancies & AI Matcher
*   **AI Auto-Fill**: Validating the AI assistant's ability to generate accurate job descriptions based solely on job titles.
*   **The Matcher**: Creating highly specific candidate profiles (e.g., "QA Automation Engineer") and asserting that the matching algorithm correctly pairs them with corresponding vacancy requirements ("Test Automation Engineer").
*   **Financials**: Validating boundary values on recruiter fees, specifically testing negative numbers and zero values.

---

## 🛠 Testing Methodology

1.  **Requirement Analysis**: Translated ambiguous business requirements into concrete, measurable pass/fail criteria.
2.  **Boundary Value Analysis**: Specifically targeted numeric fields (fees, phone numbers) and file upload limits (file count, file type).
3.  **Negative Testing Approach**: Actively attempted to "break" the system by feeding it invalid states (future dates for past actions, negative money).
4.  **Security/RBAC Testing**: Utilized URL manipulation to test endpoint protection beyond UI-level hiding.

---

## 📬 Connect With Me

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-asimsandhu-181717?style=for-the-badge&logo=github)](https://github.com/asimsandhu)

> **I build confidence in software.** By thinking like a malicious user and an impatient customer simultaneously, I find the edge cases before they find production.

</div>