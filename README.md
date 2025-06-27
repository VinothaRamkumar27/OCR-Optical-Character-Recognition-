# 📈 Automated Profit and Loss (PnL) Extraction System from Trading Screenshots

This project automates the extraction, storage, and visualization of Profit and Loss (PnL) values from screenshots captured from trading platforms like **Finvasia** and **5Paisa**. Using OCR (Optical Character Recognition), the system identifies financial values in image files, associates them with their download dates, stores the data in a **MySQL** database, and visualizes it via a **React frontend** and **Redash dashboard**.

---

## 🚀 Project Objectives

- Automatically extract PnL values from screenshots using OCR
- Organize screenshots based on trading app and download date
- Store extracted data in MySQL database, categorized by trading app
- Provide real-time graphical visualization of PnL data
- Offer an intuitive user dashboard via a React-based web frontend

---

## 🛠️ Tools & Technologies

| Component      | Tech Stack                     |
|----------------|--------------------------------|
| Language       | Python, JavaScript (React)     |
| Backend        | Python, Pytesseract, MySQL     |
| Frontend       | React.js                       |
| Image Handling | Pillow, OpenCV (optional)      |
| OCR Engine     | Tesseract                      |
| Database       | MySQL                          |
| Visualization  | Redash                         |

---

## 🗂️ Module Breakdown

### 📤 1. Uploading the Images

Screenshots from trading platforms are automatically uploaded and sorted into folders based on the **app name** and **download date**.

#### Folder Structure:
- `Finvasia/`: Stores Finvasia screenshots
- `5Paisa/`: Stores 5Paisa screenshots

Each screenshot is auto-categorized into its respective folder upon download or capture.

---

### 🔍 2. Optical Character Recognition (OCR)

OCR is used to extract PnL values from defined regions of each screenshot.

#### 🔧 Libraries Used:
- `os` – for file path handling
- `time` – to handle scanning intervals
- `PIL` / `Pillow` – for image cropping and manipulation
- `pytesseract` – Tesseract-based OCR engine
- `re` – for extracting currency values using regex
- `mysql.connector` – to connect and insert data into MySQL

#### 🔁 OCR Process Flow:
1. Monitor image folder continuously
2. Open new images and crop defined ROI
3. Extract text via `pytesseract`
4. Match and extract PnL using regex
5. Save filename, modified time, and extracted PnL into MySQL

---

### 🗃️ 3. Database Storage (MySQL)

All extracted data is stored in a structured **MySQL** database with dedicated tables for each trading platform:

#### Tables:
- `finvasia`
- `5paisa`

#### Columns:
- `filename` – name of the image file
- `modified_time` – timestamp of screenshot capture
- `pnl_value` – extracted profit or loss value

This structure ensures efficient querying, reporting, and platform-specific analysis.

---

### 📊 4. Redash Integration

[Redash](https://redash.io) is used for data exploration and dashboarding.

#### Redash Features:
- Connects directly to the MySQL database
- Allows custom SQL queries
- Visualizes PnL values through charts
- Schedules reports and dashboard refreshes

This makes the financial data more accessible and actionable for users and stakeholders.

---

### 🌐 5. React Web Dashboard

A simple, user-friendly **React-based frontend** allows users to:
- View PnL trends over time
- Compare daily profits and losses
- Analyze price movement directions
- Avoid logging into each trading account separately

#### Key Features:
- Clean UI for quick insights
- Graphical indicators for profit/loss states
- Real-time data updates from backend and MySQL
- Integrated with Redash charts

---

## 🧠 How It Works

1. Images from Finvasia/5Paisa are auto-saved to folders
2. OCR continuously monitors folders for new images
3. Text is extracted and filtered to find PnL values
4. Image name, PnL, and timestamp are stored in MySQL
5. Data is visualized via Redash and displayed in React UI

---

## Sample Output

1. Folder

![img alt](https://github.com/VinothaRamkumar27/OCR-Optical-Character-Recognition-/blob/2824b6b7de10da5b042d5cf98155dc80f628fa89/Sample%20outputs/folder.png)

2. Data Extraction

![img alt](https://github.com/VinothaRamkumar27/OCR-Optical-Character-Recognition-/blob/2824b6b7de10da5b042d5cf98155dc80f628fa89/Sample%20outputs/code%20output.jpg)

3. Database Storage

![img alt](https://github.com/VinothaRamkumar27/OCR-Optical-Character-Recognition-/blob/2824b6b7de10da5b042d5cf98155dc80f628fa89/Sample%20outputs/Database.png)

4. Redash

![img alt](https://github.com/VinothaRamkumar27/OCR-Optical-Character-Recognition-/blob/3518daf3c1a3f2834bafb20bc682ddde1125d083/Sample%20outputs/Redash.jpg)

5. Home Page

![img alt](https://github.com/Rekha050803/Automated-Financial-Data-Extraction-and-Visualization-Using-OCR-and-Redash/blob/5dfa190f746ef9700b6142c1ce764cd79c3ec039/Automated%20Financial%20Data%20Extraction%20and%20Visualization-Using%20OCR%20and%20Redash/output-screenshots/Home%20Page.png)

6. Visualisation

![img alt](https://github.com/VinothaRamkumar27/OCR-Optical-Character-Recognition-/blob/3adefc56d57dff5266186ecbe242a19408e412c1/Sample%20outputs/graph.jpg)
