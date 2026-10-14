# 🤖 AI Resume Analyzer

> An intelligent resume analysis web application built with **Streamlit** that parses resumes, predicts career fields, recommends skills and courses, and scores resumes — all in real time.

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.x-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![spaCy](https://img.shields.io/badge/spaCy-NLP-09A3D5?style=for-the-badge&logo=spacy&logoColor=white)](https://spacy.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

---

## 📖 Overview

**AI Resume Analyzer** (branded as **SmartHire**) is a full-stack Streamlit web application that helps job seekers improve their resumes and discover career opportunities. It extracts structured data from uploaded PDF resumes using NLP, predicts the most suitable career field, recommends missing skills and online courses, and generates an overall resume quality score.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📄 **PDF Resume Parsing** | Automatically extracts name, email, phone, skills, and page count from uploaded resumes |
| 🎯 **Career Field Prediction** | Identifies the candidate's likely target field (Data Science, Web Dev, Android, iOS, UI/UX) |
| 💡 **Skills Recommendation** | Suggests relevant skills to add based on the detected career path |
| 🎓 **Course Recommendations** | Recommends curated online courses and certificates with direct links |
| 📊 **Resume Score** | Scores the resume (0–100) based on the presence of key sections like Objective, Projects, Achievements, etc. |
| ✍️ **Resume Writing Tips** | Provides actionable, section-by-section improvement advice |
| 🔐 **Admin Dashboard** | Secure admin panel to view all user data, download CSV reports, and visualize analytics via Plotly pie charts |

---

## 🏗️ Project Structure

```
AI-Resume-Analyzer/
│
├── App.py                  # Main Streamlit application
├── Courses.py              # Course & YouTube video recommendation data
├── requirements.txt        # Python dependencies
├── Logo/
│   ├── SRA_Logo.ico        # App favicon
│   ├── SRA_Logo.jpg        # App logo
│   └── s6951lA.png         # Nav logo
├── Uploaded_Resumes/       # Stores uploaded resume PDFs (auto-created)
├── sc1.png                 # Screenshot – User side
├── sc2.png                 # Screenshot – Admin side
└── README.md
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend / UI** | Streamlit, Bootstrap 4 |
| **NLP / Parsing** | [PyResparser](https://omkarpathak.in/pyresparser/), [spaCy](https://spacy.io/) (`en_core_web_sm`) |
| **PDF Extraction** | [PDFMiner3](https://pypi.org/project/pdfminer3/) |
| **Database** | MySQL (via PyMySQL) |
| **Data & Visualization** | Pandas, Plotly Express |
| **Media** | Pafy (YouTube metadata) |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- [XAMPP](https://www.apachefriends.org/) or any MySQL server running locally

### 1. Clone the repository

```powershell
git clone https://github.com/Hanna-nigussie/AI-Resume-Analyzer.git
cd AI-Resume-Analyzer
```

### 2. Create and activate a virtual environment

```powershell
py -m venv venv
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```powershell
pip install -r requirements.txt
```

### 4. Download the spaCy language model

```powershell
python -m spacy download en_core_web_sm
```

### 5. Configure MySQL

Start **XAMPP** (or your MySQL server) and ensure the **MySQL** service is running.

The app connects using these defaults (configurable in `App.py`):

| Parameter | Value |
|---|---|
| Host | `localhost` |
| User | `root` |
| Password | `pass123` |
| Database | `sraa` (auto-created on first run) |

> **Note:** The `user_data` table is also created automatically on first launch.

### 6. Create the uploads directory

```powershell
mkdir Uploaded_Resumes
```

### 7. Run the application

```powershell
streamlit run App.py
```

The app will open in your browser at:

```
http://localhost:8501
```

---

## 🖥️ Usage

### 👤 User Flow

1. Navigate to `http://localhost:8501`
2. Upload your resume as a **PDF** file
3. The app will display:
   - Your extracted basic information (name, email, contact, page count)
   - Your **experience level** (Fresher / Intermediate / Experienced)
   - **Skills** detected on your resume
   - **Recommended skills** to add for your target field
   - **Recommended courses** with direct enrollment links
   - A **Resume Score** based on completeness
   - Tips on improving each resume section

### 🔐 Admin Flow

1. Set `choice = 'Admin'` in `App.py` (or enable the sidebar selector)
2. Enter credentials:
   - **Username:** `hanna123`
   - **Password:** `hanna123`
3. Access:
   - Full user data table
   - CSV download of all records
   - Pie charts for predicted fields and experience levels


---

## 🔮 Career Fields Supported

| Field | Keywords Detected |
|---|---|
| **Data Science** | TensorFlow, Keras, PyTorch, Machine Learning, Deep Learning, Flask, Streamlit |
| **Web Development** | React, Django, Node.js, PHP, Laravel, WordPress, Angular JS, JavaScript |
| **Android Development** | Android, Flutter, Kotlin, XML, Kivy |
| **iOS Development** | Swift, Xcode, Cocoa, Cocoa Touch |
| **UI/UX Design** | Figma, Adobe XD, Zeplin, Prototyping, Wireframes, Illustrator |

---

## 📦 Key Dependencies

```
streamlit
pyresparser
pdfminer3
pandas
pymysql
plotly
streamlit-tags
Pillow
pafy
spacy
```

> Install all at once with: `pip install -r requirements.txt`

---

## ⚠️ Known Issues & Limitations

- The **pafy** library requires `youtube-dl` to be installed for fetching YouTube video titles. If issues arise, video titles are hardcoded as a fallback.
- Admin login credentials are currently hardcoded in `App.py`. For production use, move them to environment variables.
- MySQL password is hardcoded — use a `.env` file or Streamlit secrets in production.

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add your feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---



<p align="center">Built with ❤️ using Streamlit & Python</p>
