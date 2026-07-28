# DC-003 — PDF Upload Fails if Document Contains Specific Images

| Field | Value |
|---|---|
| **Bug ID** | DC-003 |
| **Severity** |  Medium |
| **Priority** | P2 |
| **Module** | Candidates / CV Parsing |
| **Reported By** | QA Engineering |

---

## Summary
The bulk upload CV parser fails to process PDF documents that contain embedded images (common in modern visual CVs/Resumes). The upload process hangs or fails silently without providing a clear error message to the recruiter.

---

## Steps to Reproduce
1. Navigate to the Candidates module.
2. Click "Bulk Upload CVs".
3. Select a standard text-based PDF and a PDF containing embedded profile images/graphics.
4. Click Upload.

## Expected Result
Both CVs should upload successfully. The parser should extract text where possible and gracefully ignore unreadable image data. If parsing completely fails, a clear error message (e.g., "Could not parse document structure") should be displayed.

## Actual Result
The text-based PDF processes correctly, but the image-containing PDF causes the upload process to fail or stall. No proper error message is displayed to the user explaining why the file was rejected.

## Impact
**MEDIUM.** Creates significant friction for recruiters processing modern, graphic-heavy CVs. It requires manual data entry workarounds, slowing down operational efficiency.
