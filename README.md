# Smart File Organiser

A content-aware Python file organiser I built to organise messy folders (especially uni files) by actually reading what’s inside the files instead of just relying on filenames.

It’s designed for situations where everything is named like `Lecture 1`, `Tutorial 2`, etc., and normal file sorting doesn’t work.

---

## Tech used

- Python
- pypdf
- python-pptx
- JSON

---

## What it does

- Reads file content from:
    - PDFs
    - PowerPoint files (.pptx)

- Uses keyword scoring to figure out which subject a file belongs to (e.g. ECON104, FINC201)

- Falls back to file type if it can’t confidently classify something

- Shows a preview before moving anything (so nothing gets messed up accidentally)

- Creates folders automatically and moves files into them

- Handles duplicate filenames safely

- Ignores hidden system files like `.DS_Store`

---

## Example

Before:
Lecture 1.pdf
Lecture 2.pptx
Tutorial 3 Questions.pdf
IMG_2133.HEIC

After running:
ECON104/
FINC201/
Images/
Documents/

---

## How to run

1. Install dependencies: python3 -m pip install -r requirements.txt
2. Run the program: python3 main.py
3. Enter a folder path when prompted: /Users/yourname/Downloads/filesort_test

4. Review the preview, then confirm if you want to sort the files

---

## How it works (simple)

- Extracts text from files (PDF + PPTX)
- Cleans and tokenises the text
- Scores each subject using keywords
- Picks the best match if confidence is high
- Otherwise falls back to file type (Documents, Images, etc.)

---

## Files
- main.py → main program
- rules.json → subject keyword rules
- requirements.txt

---

## Notes

- `.ppt` (old PowerPoint format) isn’t supported for content reading, so those get sorted using fallback rules
- Some PDFs don’t extract text well (e.g. scanned files), so they may go to Documents instead

---

## Why I built this

Most file sorters just use file extensions or filenames, which doesn’t work well for uni files.

I wanted something that could actually understand what the file is about and organise it properly.

---

## Author

Tyler Kennedy  
Computer Science & Accounting  
University of Canterbury
