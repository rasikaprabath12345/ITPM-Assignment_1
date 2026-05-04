# IT3040 – Assignment 1: Transliteration Accuracy Testing
 
## Overview
 
This repository contains the Playwright-based test automation project for **IT3040 – IT Project Management**, Assignment 1, Option 1.
 
The objective is to evaluate how accurately the [PixelsSuite Chat Translator](https://www.pixelssuite.com/chat-translator) converts chat-style **Singlish** input into **Sinhala** output. The automation script tests 50 negative test cases covering all 24 Singlish input types defined in Appendix 1 of the assignment.
 
---
 
## Project Structure
 
```
it23843134/
├── it23843134.py          # Main Playwright automation script
├── it23843134.xlsx        # Test cases Excel file (input + results)
└── README.md              # This file
```
 
---
 
## Prerequisites
 
- **Python 3.11 or 3.12** — [Download here](https://www.python.org/downloads/)
- **Google Chrome** (recommended) — or let Playwright install Chromium
---
 
## Installation
 
### Step 1: Clone or download the repository
 
```bash
git clone https://github.com/rasikaprabath12345/ITPM-Assignment_1.git
cd it23843134
```
 
Or download the ZIP and extract to `C:\Users\ASUS\Desktop\it23843134`.
 
### Step 2: Install dependencies
 
Open Command Prompt and navigate to the project folder:
 
```cmd
cd /d C:\Users\ASUS\Desktop\it23843134
```
 
Then run:
 
```cmd
pip install -U pip
pip install playwright openpyxl
playwright install
```
 
---
 
## Running the Tests
 
Make sure the Excel file (`it23843134.xlsx`) is in the project folder and is **not open** in Excel.
 
Run the following command:
 
```cmd
python it23843134.py --excel "it23843134.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```
 
### What happens when you run it:
 
1. A Chrome browser opens automatically
2. The script navigates to the Chat Translator site
3. Each Singlish input is typed into the input box
4. The Sinhala output is captured and saved to the Excel file
5. Pass/Fail status is recorded automatically
> Do not close the browser while the script is running!
 
---
 
## Test Results
 
After running, open `it23843134.xlsx` to view:
 
| Column | Description |
|--------|-------------|
| TC ID | Test case ID (Neg_0001 to Neg_0050) |
| Input length type | S (≤30 chars), M (31–299 chars), L (300–450 chars) |
| Input | Singlish input text |
| Expected output | Correct Sinhala translation |
| Actual output | Output captured from the site |
| Status | PASS / FAIL |
| Singlish input types covered | Input type category |
| Evidence or rationale | Reason for the input type |
 
---
 
## Test Summary
 
- **Total test cases:** 50
- **Singlish input types covered:** All 24 types (minimum 2 per type)
- **Target:** All 50 cases should FAIL (demonstrating system weaknesses)
---
 
## Target Application
 
**URL:** https://www.pixelssuite.com/chat-translator
 
**Function tested:** Chat Sinhala transliteration (Singlish to Sinhala)
 
**Out of scope:** Standard Sinhala transliteration, backend APIs, performance/security testing
 