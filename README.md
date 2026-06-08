# We Love PDF

A clean, responsive PDF tools website prototype with 60 tool workflows.

## Run

```powershell
cd "E:\Yt Title"
npm install
npm start
```

Open `http://localhost:4173`.

The Express backend serves the frontend and exposes:

- `GET /api/health`
- `GET /api/tools`
- `POST /api/process/:tool`

## What works in this static build

The app includes all 60 tools in the UI. Supported PDF tools use the Express backend first and browser processing where that is better for preview/conversion. Current real operations include merge, split, extract, delete, reorder, rotate, duplicate, blank page insertion, watermark, page numbers, header/footer, metadata cleanup/editing, flatten-style re-save, annotation stamps, redaction blocks, Bates numbering, image-to-PDF, text/Markdown/HTML-to-PDF, PDF text extraction, PDF-to-image rendering, summary/quiz/invoice text helpers, and preview.

Some tools are intentionally marked `Server-ready` because polished production output needs backend engines:

- OCR, deskew, scan enhancement, background removal
- URL to PDF through a headless browser
- real Office conversions through LibreOffice or cloud conversion workers
- certificate-based signature verification
- AI chat/translation through an API backend
- true password encryption/decryption for strongly encrypted PDFs

## Production engine suggestions

- PDF preview: PDF.js
- Browser PDF edits: PDF-Lib
- PDF repair/security/linearization: qpdf
- Compression/raster optimization: Ghostscript, pngquant, mozjpeg
- Office conversions: LibreOffice workers
- OCR and scan cleanup: Tesseract OCR, OpenCV
- PDF rendering/extraction: Poppler or PyMuPDF
- Jobs: Redis + BullMQ or Celery
- Temporary storage: local temp folder for MVP, S3-compatible object storage later
