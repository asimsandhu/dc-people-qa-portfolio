# Test Cases — Module: Candidates & CV Management

**Module:** Candidates  
**Author:** Asim Masood  
**Domain:** DC People Platform  

---

## TC-CAND-001: Bulk Upload — Valid Formats (PDF & DOCX)
*   **Type**: Functional / Positive
*   **Steps**: 
    1. Navigate to Candidate module. 
    2. Click Bulk Upload. 
    3. Select a mix of valid `.pdf` and `.docx` files.
*   **Expected Result**: System processes all files, parses data, and successfully creates candidate profiles.
*   **Status**: PASSED

## TC-CAND-002: Bulk Upload — Invalid Formats
*   **Type**: Negative Testing
*   **Steps**: 
    1. Click Bulk Upload. 
    2. Select non-document files (e.g., `.exe`, `.jpg`).
*   **Expected Result**: System rejects the upload immediately and displays an "invalid file type" error message.
*   **Status**: PASSED

## TC-CAND-003: Bulk Upload — Batch Size Limit
*   **Type**: Boundary Value Analysis
*   **Steps**: 
    1. Click Bulk Upload. 
    2. Select 11 valid PDF files (system limit is 10).
*   **Expected Result**: System prevents upload and displays limit exceeded error.
*   **Status**: PASSED

## TC-CAND-004: LinkedIn Import Scraper
*   **Type**: Integration / Functional
*   **Steps**: 
    1. Click Add Candidate. 
    2. Select LinkedIn Import. 
    3. Paste a valid LinkedIn profile URL and click Scrape.
*   **Expected Result**: Modal closes automatically, and candidate profile is populated with scraped data.
*   **Status**: FAILED (Modal hangs; data scraping unreliable).

## TC-CAND-005: Data Validation — Phone Number Field
*   **Type**: Negative Testing
*   **Steps**: 
    1. Open an existing Candidate profile for editing. 
    2. Enter alphabetic characters (`ABCxyz`) into the phone number field. 
    3. Save.
*   **Expected Result**: Form validation prevents saving and highlights the phone field with an error.
*   **Status**: FAILED (System accepts invalid data types).

## TC-CAND-006: Logic Validation — Future Dates in Contact History
*   **Type**: Logic / Edge Case
*   **Steps**: 
    1. Add a Note to a Candidate. 
    2. Select the radio button for "Has candidate been contacted?". 
    3. Select a date in the future.
*   **Expected Result**: System should prevent selecting future dates for past contact actions.
*   **Status**: FAILED.