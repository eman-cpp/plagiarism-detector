# 🔍 Plagiarism Detector and Similarity Analyzer

**An Object-Oriented C++ Desktop Application**

A desktop-based plagiarism detection and text similarity analysis tool developed using **C++ and Qt Framework**. The application compares multiple text documents using different similarity algorithms, identifies matching phrases, displays similarity percentages, and maintains a permanent history of previous analyses.

---

## 📌 Project Overview

The Plagiarism Detector and Similarity Analyzer is designed to help students, teachers, and other users identify similarities between text documents.

Instead of manually reading and comparing documents, users can upload TXT files and analyze them using three different similarity detection techniques:

- **Jaccard Similarity:** Measures similarity based on common unique words.
- **Cosine Similarity:** Compares the frequency of words in two documents.
- **N-Gram Similarity:** Identifies matching groups of three consecutive words.

The application provides a graphical user interface (GUI), making it easy to upload documents, select analysis methods, view results, and generate reports.

**Important:** The application measures textual similarity. A high similarity percentage is not automatic proof of plagiarism because quotations, references, and commonly used phrases can also produce matching results.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 📂 Document Upload | Load and view TXT documents using an Open File button. |
| 🧹 Text Cleaning | Convert text to lowercase, remove punctuation and extra spaces, and tokenize words. |
| 📊 Jaccard Analysis | Compare documents based on common unique words. |
| 📈 Cosine Analysis | Compare documents using word frequency. |
| 🔗 N-Gram Analysis | Identify matching three-word phrases. |
| ⚖️ Pairwise Comparison | Compare two documents and display their similarity percentage. |
| 📚 Compare All | Compare every possible pair of loaded documents. |
| 🔎 Matching Phrases | Display common phrases found in documents. |
| 🕘 Analysis History | Automatically save and retrieve previous analyses. |
| 📄 Report Generation | Generate formatted reports for individual analyses. |
| 🖥️ Graphical Interface | User-friendly desktop interface with buttons, text boxes, and result tables. |
| ⚠️ Error Handling | Display understandable error messages for invalid or missing input. |

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| C++ | Main programming language |
| Qt Framework | Desktop graphical user interface |
| Qt Creator | Development environment |
| MinGW | C++ compiler |
| Git | Version control |
| Git Bash | Git command-line operations |
| GitHub | Remote repository and collaboration |
| draw.io | UML class diagrams |

### Libraries and C++ Features

- STL `vector` – Store documents and analysis results.
- STL `map` – Store word frequencies.
- STL `set` – Store unique words and phrases.
- STL `algorithm` – Sorting and searching.
- `ifstream` – Read input documents.
- `ofstream` – Save reports and history.
- Templates – Generic sorting functionality.
- Exception Handling – Manage application errors.

---

## 🏗️ Object-Oriented Programming Concepts

This project demonstrates the major OOP concepts covered in our university course.

| OOP Concept | Implementation |
|---|---|
| Classes and Objects | Document, Analyzer, AnalysisResult, Report, and other classes. |
| Constructors | Initialize document and analysis objects. |
| Destructors | Manage object cleanup and memory resources. |
| Function Overloading | Multiple versions of the `analyze()` function. |
| Function Overriding | Each similarity analyzer implements its own analysis method. |
| Static Members | Track total documents and generate unique analysis IDs. |
| Friend Function/Class | Report accesses private AnalysisResult information. |
| Operator Overloading | Compare and print analysis results using overloaded operators. |
| Inheritance | TextDocument inherits Document; analyzers inherit SimilarityAnalyzer. |
| Multiple Inheritance | AnalysisResult inherits Printable and Exportable. |
| Polymorphism | Runtime selection of the appropriate similarity algorithm. |
| Exception Handling | Custom exceptions with try-catch blocks. |
| Templates | Generic `sortDescending<T>()` function. |
| STL | Vector, map, set, sort, and find_if. |
| File Handling | Read TXT documents and save CSV history and reports. |

---

## 🧩 Proposed Class Structure

The application is divided into separate classes, each responsible for a particular task.

| Class | Responsibility |
|---|---|
| `Document` | Stores document name and content. Tracks total documents. |
| `TextDocument` | Inherits Document and handles text cleaning and word extraction. |
| `SimilarityAnalyzer` | Abstract parent class declaring the common `analyze()` function. |
| `JaccardAnalyzer` | Calculates Jaccard similarity. |
| `CosineAnalyzer` | Calculates cosine similarity using word frequencies. |
| `NGramAnalyzer` | Identifies matching three-word phrases. |
| `AnalysisResult` | Stores document names, analysis method, similarity score, and matching phrases. |
| `Printable` | Provides a common printing interface. |
| `Exportable` | Provides a common exporting interface. |
| `Report` | Generates formatted reports from analysis results. |
| `FileManager` | Reads documents and handles file operations. |
| `HistoryManager` | Saves and retrieves previous analysis results. |
| `MainWindow` | Provides the graphical interface and connects application components. |

---

## ⚙️ How the Application Will Work

The planned application workflow is:

1. Launch the desktop application.
2. Upload two or more TXT documents.
3. The application reads and cleans the document contents.
4. Select a similarity detection method.
5. The selected analyzer processes the documents.
6. The application calculates the similarity percentage.
7. Matching phrases are identified and displayed.
8. Results are arranged according to similarity scores when comparing multiple documents.
9. The analysis is automatically saved in the history file.
10. Users can generate and save a report.

---

## 📊 Similarity Detection Methods

### 1. Jaccard Similarity

Measures the similarity between two documents by comparing their unique word sets.

**Formula:**

J(A, B) = |A ∩ B| / |A ∪ B| × 100

Where:
- A = Unique words in Document 1.
- B = Unique words in Document 2.
- Intersection = Common words.
- Union = All unique words from both documents.

### 2. Cosine Similarity

Measures similarity by comparing the frequency of words in two documents.

**Formula:**

Cosine Similarity = (A · B) / (||A|| × ||B||) × 100

This method helps identify documents that use similar vocabulary, even when word frequencies differ.

### 3. N-Gram Similarity

Divides document text into groups of three consecutive words and identifies matching groups.

Example:

Document 1:
`Software engineering is an interesting field`

Document 2:
`Software engineering is a growing field`

Common three-word phrase:

`Software engineering is`

The application will display matching phrases to help users understand where similarities occur.

---

## 💾 File Handling and Data Storage

The application will use local files to preserve information between sessions.

| File Type | Purpose |
|---|---|
| `.txt` | Input documents and generated text reports |
| `.csv` | Analysis history |

### Analysis History Format

The CSV history file will contain:

```csv
id,document1,document2,method,score,timestamp
1,assignment1.txt,assignment2.txt,Jaccard,75.50,2026-11-21
```

The application will:
- Load existing history when it starts.
- Automatically create the history file if it does not exist.
- Save every new analysis.
- Preserve previous results after closing the application.
- Display appropriate errors when files cannot be accessed or contain invalid input.

---

## 🖥️ Installation and Setup

### Prerequisites

Before running the project, install:

1. **Qt Creator** – Development environment.
2. **Qt Framework** – Required for the graphical interface.
3. **MinGW Compiler** – C++ compilation.
4. **Git** – Version control.
5. **Git Bash** – Git commands.

### Step 1: Clone the Repository

Open Git Bash and execute:

```bash
git clone https://github.com/eman-cpp/plagiarism-detector.git
```

### Step 2: Open the Project

1. Launch Qt Creator.
2. Select **File → Open File or Project**.
3. Navigate to the cloned project folder.
4. Open the project's `.pro` or `CMakeLists.txt` file, depending on the configured Qt project.
5. Select the MinGW kit compatible with the installed Qt version.

### Step 3: Build and Run

1. Wait for Qt Creator to configure the project.
2. Click the Build button.
3. Resolve any compilation errors.
4. Click Run to launch the application.

**Note:** Exact build instructions may be updated when the final project structure and Qt build configuration are established.

---

## 🔬 Testing Plan

The application will be tested using different document combinations.

| Test Case | Expected Result |
|---|---|
| Two identical documents | Approximately 100% similarity. |
| Two completely different documents | Near 0% similarity. |
| Partially similar documents | An intermediate similarity score. |
| Documents with common phrases | Matching phrases displayed. |
| Empty document | Appropriate error message. |
| Missing document | File error displayed. |
| Invalid GUI input | Input rejected safely. |
| Application restarted | Previous analysis history restored. |

---

## 👥 Team Members

**Bahria University – H11 Campus Islamabad**

Department of Software Engineering

**Course:** Object-Oriented Programming Lab  
**Class:** BSE-3B – Fall 2026

| Member | Registration Number | Responsibilities |
|---|---|---|
| Ali Mansoor | 09-131252-042 | Document classes, file management, history, reports, custom exceptions, static members, and interfaces. |
| Eman | 09-131252-096 | Similarity algorithms, text cleaning, analysis results, operator overloading, templates, STL, and polymorphism. |

### Shared Responsibilities

Both members will work together on:

- GUI development using Qt.
- Input validation and testing.
- README and final documentation.
- GitHub collaboration and version control.
- Regular commits using Git Bash.
- Understanding the complete project for the final viva.

---

## 🌿 Version Control and Collaboration

Git and GitHub will be used to maintain the project and track changes made by both team members.

### Basic Git Commands

Clone the repository:

```bash
git clone https://github.com/eman-cpp/plagiarism-detector.git
```

Check modified files:

```bash
git status
```

Add changes:

```bash
git add .
```

Commit changes:

```bash
git commit -m "Add document management classes"
```

Push changes:

```bash
git push
```

Get the latest changes:

```bash
git pull
```

Both team members will make regular commits to maintain a clear development history and avoid losing work.

---

## 🎯 Project Goals

The main goal is to develop a functional, user-friendly plagiarism detection and similarity analysis application while demonstrating practical implementation of Object-Oriented Programming concepts in C++.

The project also aims to improve our understanding of:

- Real-world C++ application development.
- GUI development using Qt.
- Algorithm implementation.
- File handling and data persistence.
- Software design and class relationships.
- Version control and teamwork.

---

## 📌 Project Status

**Development Stage:** Academic OOP Lab Project – Fall 2026

The features and implementation described in this README represent the approved project proposal and planned development scope. Features will be marked complete as they are implemented and tested.

---

## 📜 Academic Information

Developed as a group project for the Object-Oriented Programming Lab at Bahria University, H11 Campus, Islamabad.

**Course Instructor:** Engr. Aleem Ahmed

**Lab Engineer:** Engr. Saad Mazhar Khan

---

⭐ *Built with C++, Qt, and Object-Oriented Programming.*
