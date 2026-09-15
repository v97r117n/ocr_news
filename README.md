# Eenadu imgmain2 Telugu OCR

Downloads only `#imgmain2` page images from Eenadu epaper pages, runs Telugu OCR, and writes JSON.

## Setup

```bash
python3 -m pip install -r requirements.txt
python3 -m playwright install chromium
brew install tesseract tesseract-lang
```

## Run main + all district editions

```bash
python3 scrape_ocr.py --date 14/09/2026 --out output/all.json
```

Date range:

```bash
python3 scrape_ocr.py --date 13/09/2026..14/09/2026 --out output/all.json
```

By default, the script processes the main paper plus all known district/other editions and all available pages in each edition.

## Single edition only

```bash
python3 scrape_ocr.py --date 13/09/2026 --eid 10 --out output/guntur.json
```

## Output fields

Each JSON record includes `date`, `eid`, `edition`, `page_index`, `imgmain2_url`, `image_path`, `text`, and optional `error`.
