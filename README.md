# Exam Timetabling using Graph Coloring on Student-Course Registrations

## 📌 Project Overview
This project applies **Graph Theory and Coloring Algorithms** to generate an exam timetable from student-course registration data.  
The idea is that each course is represented as a **node**, and an edge is drawn between two courses if there are students enrolled in both.  
Using **graph coloring**, courses that share students are assigned to different exam periods (colors), ensuring no student has two exams at the same time.

---

## 📊 Dataset
- Source: `studentcourses.xlsx` (contains multiple sheets for different faculties such as Medical Sciences, Pharmacy, Engineering, Computer Science, etc.)
- Columns:  
  - `رقم الطالب` (Student ID)  
  - `اسم الطالب` (Student Name)  
  - `التخصص` (Major)  
  - `رقم المقرر` (Course ID)  
  - `اسم المقرر` (Course Name)  
  - `رمز المقرر` (Course Code)  
  - `رقم الشعبة` (Section ID)  

---

## ⚙️ Project Workflow
1. **Data Preprocessing**
   - Load and merge data from different faculty sheets
   - Clean duplicates and handle missing values
   - Properly format Arabic text for visualization

2. **Graph Construction**
   - Courses = Nodes  
   - Edges = Two courses taken by the same student  
   - Course degree = Number of connections with other courses  

3. **Exploratory Analysis**
   - Distribution of students across courses
   - Top 50 courses by student count
   - Top 100 courses by degree (number of connections)

4. **Visualization**
   - Bar plots of student enrollment
   - Scatter plots of course degrees
   - Network graph of courses

5. **Graph Coloring (Exam Timetabling)**
   - Applied multiple greedy coloring strategies:
     - `largest_first`
     - `random_sequential`
     - `smallest_last`
     - `independent_set`
     - `connected_sequential_dfs`
     - `connected_sequential_bfs`
     - `saturation_largest_first`
   - Compared number of colors (exam periods) and execution time for each strategy.

---

## 📈 Results
- Generated an exam timetable where no student has overlapping exams.
- Compared algorithms and found `saturation_largest_first` provides efficient coloring with fewer exam periods.
- Visualized the full course network with assigned exam slots.

---

## 🛠️ Technologies Used
- **Python**
- Libraries: `pandas`, `numpy`, `networkx`, `matplotlib`, `seaborn`, `arabic_reshaper`, `bidi.algorithm`, `time`

---

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/exam-timetabling.git
