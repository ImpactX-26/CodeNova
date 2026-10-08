# 🧠 MisconceptionHunter

### AI-Powered Multi-Agent System for Detecting and Correcting Student Misconceptions

**MisconceptionHunter** is an AI-powered educational system designed to identify the **underlying misconception behind a student's incorrect answer**, rather than simply marking the answer as right or wrong.

The system uses a multi-agent architecture where one AI agent analyzes the student's response and a separate verification agent independently evaluates the detected misconception. Based on the verified misconception, the system generates a personalized challenge to help the student understand the concept correctly.

---

## 🎯 Problem Statement

Traditional educational systems generally focus on whether a student's answer is **correct or incorrect**.

However, an incorrect answer does not always reveal *why* the student made the mistake.

For example:

> **Question:** Why does a moving object continue moving after the applied force is removed?

A student might answer:

> "The object keeps moving because a force is continuously acting on it."

Simply marking this answer as incorrect does not identify the student's underlying misunderstanding.

MisconceptionHunter attempts to identify the reasoning error and provide targeted feedback.

---

## 💡 Our Solution

MisconceptionHunter follows a multi-stage AI pipeline:

```text
              Student Question
                     │
                     ▼
              Student Answer
                     │
                     ▼
          ┌─────────────────────┐
          │   Analysis Agent    │
          │     (Groq LLM)      │
          └──────────┬──────────┘
                     │
                     ▼
          Detected Misconception
                     │
                     ▼
          ┌─────────────────────┐
          │   Verifier Agent    │
          │   (Gemini LLM)      │
          └──────────┬──────────┘
                     │
                     ▼
          Verified Misconception
                     │
                     ▼
          ┌─────────────────────┐
          │ Personalized        │
          │ Challenge Generator │
          └──────────┬──────────┘
                     │
                     ▼
             Targeted Learning
```

---

## 🤖 Multi-Agent Architecture

### 1. Analysis Agent

The first AI agent analyzes:

* The question
* The student's answer
* The underlying reasoning
* Possible conceptual errors
* The likely misconception

It produces a structured analysis rather than simply returning "correct" or "incorrect."

### 2. Verifier Agent

The second agent independently evaluates the Analysis Agent's output.

It checks:

* Whether the identified misconception is reasonable
* Whether the reasoning is scientifically/conceptually correct
* Whether the student's actual answer supports the detected misconception
* Whether the correction provided is accurate

The verifier can classify the result as:

* **Confirmed**
* **Partially Confirmed**
* **Not Confirmed**

It also provides a confidence level and a simplified correction.

Using a different LLM provider for verification provides **cross-model evaluation**, rather than asking the same model to verify its own output.

### 3. Personalized Challenge Generator

After the misconception is verified, the system generates a targeted challenge related to the student's conceptual weakness.

The goal is to move from:

**Mistake → Understanding → Practice**

rather than simply providing the correct answer.

---

## ✨ Key Features

* 🧠 AI-based misconception detection
* 🔍 Independent verification of AI analysis
* 🎯 Personalized learning challenges
* 📚 Concept-focused feedback
* 🤖 Multi-agent architecture
* 💬 Natural-language interaction
* 📊 Confidence-based verification
* 🌐 Interactive Gradio interface
* ☁️ Google Colab compatible
* 🔐 API keys entered securely at runtime

---

## 🛠️ Technology Stack

| Technology    | Purpose                               |
| ------------- | ------------------------------------- |
| Python        | Core development                      |
| Groq API      | Analysis Agent                        |
| Gemini API    | Verification Agent                    |
| Gradio        | Interactive user interface            |
| Google Colab  | Development and execution environment |
| LLM Prompting | Reasoning and misconception analysis  |

---

## 🔄 How It Works

### Step 1 — Student Input

The student provides:

* A question
* Their answer

### Step 2 — AI Analysis

The Analysis Agent examines the response and identifies the possible misconception.

### Step 3 — Independent Verification

The Verifier Agent receives the original question, student answer, and analysis.

It independently evaluates whether the detected misconception is valid.

### Step 4 — Correction

The system provides a simple explanation of the correct concept.

### Step 5 — Personalized Challenge

A new challenge is generated specifically around the identified misconception.

This allows the student to practice the concept instead of simply seeing the correct answer.

---

## 📌 Example

### Student Question

**Why does a moving object continue moving after the force pushing it is removed?**

### Student Answer

> "It keeps moving because the pushing force remains inside the object."

### Analysis Agent

Possible misconception:

> The student believes that continuous force is required to maintain motion.

### Verifier Agent

**Verification:** Confirmed

**Confidence:** High

**Correct Concept:**

According to Newton's First Law, an object in motion continues moving with constant velocity when no net external force acts on it.

### Personalized Challenge

The system generates another conceptual question designed to test whether the student now understands the role of net force and inertia.

---

## 🎨 User Interface

The project uses **Gradio** to provide an interactive interface where users can enter a question and answer and receive:

* Analysis Agent output
* Verifier Agent output
* Verified misconception
* Correct concept
* Personalized challenge

---

## 🔐 API Key Security

API keys are **not hard-coded into the project**.

They are entered at runtime using Python's `getpass` functionality.

Example:

```python
from getpass import getpass

GROQ_API_KEY = getpass("Enter your Groq API key: ")
```

Similarly, the Gemini API key is entered at runtime.

**Never commit API keys, passwords, or other secrets to GitHub.**

---

## 🚀 Running the Project

### Option 1 — Google Colab

1. Open `MisconceptionHunter.ipynb`.
2. Run the notebook cells in order.
3. Enter your Groq API key when prompted.
4. Enter your Gemini API key when prompted.
5. Run the Gradio interface.
6. Enter a question and student answer.
7. View the analysis, verification, and personalized challenge.

### Option 2 — Local Environment

Clone the repository:

```bash
git clone https://github.com/ImpactX-26/CodeNova.git
cd CodeNova
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

Run the notebook or application according to the project setup.

---

## 📂 Project Structure

```text
CodeNova/
│
├── MisconceptionHunter.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🎯 Objectives

The main objectives of MisconceptionHunter are:

1. Identify the reasoning behind incorrect answers.
2. Detect conceptual misconceptions using AI.
3. Independently verify the detected misconception.
4. Provide simple and understandable corrections.
5. Generate personalized practice challenges.
6. Create a more adaptive learning experience.

---

## 🌍 Potential Applications

MisconceptionHunter can be extended to:

* 📚 School and college education
* 🧑‍🏫 AI teaching assistants
* 🎓 Personalized learning platforms
* 📝 Online assessment systems
* 🤖 Intelligent tutoring systems
* 📊 Learning analytics
* 💻 Coding education
* 🔬 STEM education

---

## 🔮 Future Scope

Future versions could include:

* Student misconception history
* Learning-progress tracking
* Subject-specific misconception databases
* Retrieval-Augmented Generation (RAG)
* Teacher dashboards
* Automated assessment reports
* Voice-based interaction
* Multilingual support
* Knowledge graphs for concept relationships
* More specialized verification models
* Offline/local LLM support

---

## 🏆 Hackathon Context

**Project:** MisconceptionHunter
**Team:** CodeNova
**Event:** IMPACTX '26
**Category:** Agentic AI / Educational Technology

The project demonstrates how multiple AI agents can collaborate to analyze, verify, and respond to a student's conceptual misunderstanding.

---

## 👥 Team CodeNova

Built by **Team CodeNova** for IMPACTX '26.

---

## 📜 License

This project is developed for educational and hackathon purposes.

---

## ⭐ Project Vision

> **Don't just tell students that they are wrong. Find out why they are wrong — and help them learn from it.**

**MisconceptionHunter — From Wrong Answers to Better Understanding.**
