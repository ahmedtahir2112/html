# Program Transfer Planner

## 1. Overview

This project is a web application that helps students plan a transfer from one academic program to another by showing course equivalencies.

The system:
- Displays all courses (completed, failed, and in progress)
- Indicates whether each course is passed
- Allows selection of a target program
- Generates an equivalency table for completed courses

**Current Program:** Computer Science

---

## 2. Features

- Dynamic course table generated using JavaScript
- Dropdown menu for selecting a target program
- "Transfer" button to generate equivalency results
- Only passed courses are included in equivalency
- Courses without matches are labeled as **"N/A"**
- Clean UI using HTML, CSS, and JavaScript

---

## 3. Course List

The application includes:

- Completed courses (Passed = Yes)
- Failed or in-progress courses (Passed = No)
- 5 additional courses (always marked as Yes)

### Example

| Course | Passed |
|--------|--------|
| Introduction to Artificial Intelligence | Yes |
| Computer Organization | Yes |
| Calculus II | No |
| Data Structures | No |
| Operating Systems | Yes |

---

## 4. Equivalency Algorithm

The equivalency between courses is determined using a **mapping-based approach**.

### Steps

1. User selects a target program from the dropdown
2. User clicks the **Transfer** button
3. System loops through all courses
4. Only courses with `passed = true` are considered
5. Each course is checked against a predefined mapping
6. If a match exists → equivalent course is returned
7. If no match → `"N/A"` is returned

---

### Example Mapping Table

| Course | Computer Engineering Equivalent |
|--------|-------------------------------|
| Programming Fundamentals | C Programming |
| Operating Systems | Operating Systems |
| Database Systems | Database Systems |

---

### Code Implementation

```javascript
function getEquivalent(course, program) {
    return (mappings[program] && mappings[program][course]) || "N/A";
}


## 5. Improvement Plan (Future Work)

Automatic Syllabus Comparison Using AI

The current system uses manual mappings. This can be improved using Artificial Intelligence to automatically detect course equivalency.

Proposed Algorithm

1. Data Collection
Collect syllabi of courses from both programs
Sources: PDFs, university websites, databases

2. Text Extraction
Convert documents into plain text
Remove formatting and unnecessary symbols

3. Text Processing
Tokenization (split text into words)
Remove stop words (e.g., "the", "and")
Apply stemming or lemmatization

4. Feature Representation

Convert text into numerical vectors using:

TF-IDF
Word embeddings
Transformer models (e.g., BERT)

5. Similarity Calculation
Use cosine similarity to compare courses
Measure how similar two syllabi are

6. Decision Rule
If similarity score > 0.75 → equivalent
Otherwise → "N/A"

7. Output
Automatically generate equivalency table
Display results in the application
Benefits
More accurate than manual mapping
Scalable to multiple programs/universities
Reduces human bias
Updates automatically with new syllabi
Possible Technologies
Python
NLP libraries (NLTK, spaCy)
Transformer models (BERT)
API integration with web apps



This project demonstrates a simple and effective way to visualize course equivalencies for program transfer.

Although the current system uses predefined mappings, future AI-based improvements can make it more accurate, automated, and scalable.
