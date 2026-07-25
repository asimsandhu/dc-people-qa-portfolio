# Test Cases — Module: Vacancies & AI Matcher

**Module:** Vacancies & Matcher  
**Author:** Asim Masood  
**Domain:** DC People Platform  

---

## TC-VAC-001: AI Auto-fill Job Description
*   **Type**: Functional / AI Integration
*   **Steps**: 
    1. Click Add Vacancy. 
    2. Enter a Job Title (e.g., "Senior React Developer"). 
    3. Click "Fill with AI".
*   **Expected Result**: The AI successfully generates and populates the job description, requirements, and responsibilities fields with appropriate context.
*   **Status**: PASSED

## TC-VAC-002: Document Extraction for Job Description
*   **Type**: Functional
*   **Steps**: 
    1. Click Add Vacancy. 
    2. Upload a `.txt` file containing a full job description.
*   **Expected Result**: The system extracts the text and populates the Vacancy fields correctly.
*   **Status**: FAILED.

## TC-VAC-003: External Recruiter Fee — Negative Value
*   **Type**: Boundary / Negative
*   **Steps**: 
    1. Create or edit a Vacancy. 
    2. Navigate to External Recruiter Fee. 
    3. Enter a negative numerical value (e.g., `-500`). 
    4. Save.
*   **Expected Result**: System rejects the negative value as fees cannot be less than zero.
*   **Status**: FAILED.

## TC-MAT-001: AI Matcher — Specific Role Alignment
*   **Type**: Functional / E2E
*   **Steps**: 
    1. Upload a CV specifically tailored for a "QA Automation Engineer". 
    2. Create a specific Vacancy titled "Test Automation Engineer". 
    3. Run the Matcher algorithm.
*   **Expected Result**: The candidate appears in the highly-matched / recommended column for that specific vacancy.
*   **Status**: FAILED (Algorithm failed to recognize synonym roles).