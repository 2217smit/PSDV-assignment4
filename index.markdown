---
title: "nbgrader: Automating Jupyter Notebook Grading"
layout: home
date: 2025-02-24
author: "Smit Bambhroliya, Sunay Desai, Path Bhimani"
categories: [Jupyter, Grading, Automation]
permalink: /
---

## **Introduction**  

Grading assignments in Jupyter Notebooks manually can be a tedious and inconsistent process. **Nbgrader** is an open-source tool designed to automate grading while still allowing manual feedback when necessary. It is widely used in educational settings, particularly for large-scale courses where efficiency and accuracy are critical.  

With features like **auto-grading, assignment distribution,** and **seamless integration with JupyterHub**, nbgrader streamlines the workflow for both instructors and students. It supports various grading functionalities, such as predefined test cases, manual adjustments, and structured feedback, making it one of the most versatile grading solutions for Jupyter environments.  

### Key Use Cases  
- Automating grading of coding assignments using predefined test cases.  
- Providing structured feedback to students within Jupyter Notebooks.  
- Managing assignments in large classes with seamless distribution and collection tools.  

For a complete guide and tutorials, visit the official nbgrader documentation: [nbgrader.readthedocs.io](https://nbgrader.readthedocs.io/)  

## **Installation & Setup**

### Prerequisites  
- Python (>=3.6)  
- Jupyter Notebook or JupyterLab  
- An existing JupyterHub setup (optional, but useful for multi-user environments)  

### Installation Steps  
Install nbgrader via pip:

```bash
pip install nbgrader
```
Or if you use [Jupyter Notebook](https://jupyter.org/) via [Anaconda](https://www.anaconda.com/download):

```bash
conda install -c conda-forge nbgrader
```


![](./assets/ss/ss1.png)

![](./assets/ss/ss2.png)

Configure nbgrader:

```bash
nbgrader quickstart my_course
```

This sets up the necessary directory structure for an nbgrader course.  

## **Key Features & Explanation**

### 1. Automated Grading  
Nbgrader allows instructors to create assignments with test cases that automatically evaluate student responses. This eliminates manual checking for objective questions, reducing grading time.  

**Example:**
```python
# Autograded answer
def add_numbers(a, b):
    return a + b  # Expected answer

# Test case
assert add_numbers(2, 3) == 5
```

### 2. Manual Grading & Feedback  
For subjective responses, instructors can manually grade submissions and provide detailed feedback.  

**Example:**
```python
# Manually graded cell
feedback = "Great approach, but try optimizing your solution."
score = 8  # Adjust score manually
```

### 3. Assignment Management  
Nbgrader streamlines the creation, release, and collection of assignments.  

**Example:**
```bash
# Assign an exercise
nbgrader assign problem_set_1

# Collect student submissions
nbgrader collect
```

### 4. Integration with JupyterHub  
Nbgrader seamlessly integrates with JupyterHub, ensuring assignments are securely managed without conflicts between students.  

### 5. Version Control & Regrading  
Nbgrader maintains different versions of student submissions, allowing instructors to track changes and regrade assignments if necessary.  

**Example:**
```bash
# Regrade an assignment
nbgrader autograde problem_set_1 --force
```

### 6. Plagiarism Detection  
Nbgrader can be combined with external tools like **Turnitin** or **MOSS** for academic integrity verification.  

## **Code Examples**

### Example 1: Creating an Auto-Graded Question  
```python
# Autograded answer
def square(x):
    return x ** 2  # Expected answer

# Test case
assert square(3) == 9
```

### Example 2: Collecting and Grading Assignments  
```bash
# Collect all student submissions
nbgrader collect

# Automatically grade submissions
nbgrader autograde assignment_1
```

### Example 3: Manually Adjusting Scores in the Gradebook  
```python
from nbgrader.api import Gradebook

gb = Gradebook("sqlite:///gradebook.db")

# Fetch student submission
submission = gb.find_submission("assignment_1", "student_1")

# Update score
submission.score = 85

# Save changes
gb.commit()
```

### Example 4: Adding a Custom Test Case  
```python
# Define a function to test
def multiply(a, b):
    return a * b

# Custom test case
assert multiply(4, 5) == 20
```

### Example 5: Exporting Grades to CSV  
```bash
# Export grades to a CSV file
nbgrader export --to=grades.csv
```

## **Use Cases**

### 1. University Courses  
Used in university settings to evaluate large numbers of student assignments efficiently.  

### 2. Coding Bootcamps  
Automates exercises, tracks student progress, and offers structured coding challenges.  

### 3. MOOCs (Massive Open Online Courses)  
Scales assignment evaluations without requiring a large teaching staff.  

### 4. Corporate Training Programs  
Used for assessing employee learning and progress in technical training programs.  

### 5. Data Science & Machine Learning Workshops  
Provides structured exercises with real-world datasets.  

### 6. Research and Lab Work  
Useful in scientific research and lab courses where experiments require structured assessment.  

## **Conclusion**  

Overall, **nbgrader** is a powerful tool for automating assignment grading in Jupyter Notebooks. Its structured workflow simplifies assignment creation, collection, and evaluation, making it particularly useful for large-scale educational settings.  

While nbgrader excels in auto-grading, its full potential is realized when integrated with other Python libraries, allowing for more sophisticated assessments. Its seamless integration with **JupyterHub** makes it a practical choice for scalable assessment solutions.  

## **References & Further Reading**  

- [Nbgrader documentation](https://nbgrader.readthedocs.io/en/stable/)  
- [JupyterHub: Multi-User Jupyter Environments](https://jupyterhub.readthedocs.io/en/stable/)  
- [Jupyter Notebook Extensions](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/)  
