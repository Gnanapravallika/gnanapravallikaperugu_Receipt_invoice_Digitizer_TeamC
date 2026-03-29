# Receipt & Invoice Digitizer (25% Prototype)

A simple Flask web application that extracts text from receipts (Image/PDF) using Tesseract OCR, parses key information (Date, Total, Vendor), and exports the data to CSV.

## Prerequisites

This is a **Windows-based** guide. You need the following installed:

1.  **Python 3.x**
2.  **Tesseract-OCR**
    *   Download the installer from [UB-Mannheim/tesseract/wiki](https://github.com/UB-Mannheim/tesseract/wiki).
    *   Install it (e.g., to `C:\Program Files\Tesseract-OCR`).
    *   **Important**: Add `C:\Program Files\Tesseract-OCR` to your System PATH environment variable.
3.  **Poppler** (Required for PDF processing)
    *   Download the latest binary from [poppler-windows](https://github.com/oschwartz10612/poppler-windows/releases/).
    *   Extract the zip file.
    *   Add the `bin` folder (e.g., `C:\Program Files\poppler-xx\bin`) to your System PATH environment variable.

## Installation

1.  **Clone/Download** this project to your local machine.
2.  **Install Python Dependencies**:
    Open a terminal in the project folder and run:
    ```bash
    pip install -r requirements.txt
    ```

## How to Run

1.  Start the application:
    ```bash
    python app.py
    ```
2.  Open your browser and go to:
    ```
    http://127.0.0.1:5000/
    ```

## Usage

1.  Click **Choose File** and select a receipt image (`.png`, `.jpg`) or PDF.
2.  Click **Upload & Digitize**.
3.  The system will extract text and attempt to find the Vendor, Date, and Total.
4.  Verify the data on the screen.
5.  Click **Download CSV** to save the structured data.

## Project Structure

*   `app.py`: Main Flask application logic (OCR, regex parsing).
*   `templates/index.html`: Simple frontend for file upload.
*   `uploads/`: Temporary folder for uploaded files.
*   `output/`: Folder where generated CSV files are saved.
*   `requirements.txt`: List of Python libraries.

## Notes

*   This is a 25% prototype. The extraction logic uses simple Regular Expressions and may not work for all receipt formats.
*   If Tesseract is not found, ensure it is in your PATH or update the `pytesseract.pytesseract.tesseract_cmd` path in `app.py`.
