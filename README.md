# Circular-Linked-List-Job-Scheduler
This project implements a Circular Linked List Job Scheduler in C++, designed to manage and execute jobs in a cyclic manner. The system allows dynamic job addition, deletion, execution, and display while maintaining a circular linked list structure.

Features
✅ Dynamic Job Management – Add and delete jobs without fixed size limitations.
✅ Fair Round-Robin Execution – Ensures all jobs get executed before the cycle restarts.
✅ Automatic & Continuous Processing – No need to reset after reaching the last job.
✅ Efficient Monitoring – Displays all active jobs in real-time.

How It Works
1️⃣ Jobs are added dynamically (e.g., Data Backup, Image Rendering, System Health Check).
2️⃣ Execution follows a circular pattern, moving from job to job automatically.
3️⃣ Jobs can be deleted, and the structure remains intact.
4️⃣ Real-time job queue display enables easy monitoring.

Code Structure
JobNode Struct – Represents each job (Job ID, Name, Execution Time).

JobScheduler Struct – Manages the circular linked list.

Functions:

addJob() – Inserts a job dynamically.

deleteJob() – Removes a job while maintaining the circular structure.

executeJobs() – Executes jobs in a cyclic order.

displayJobs() – Displays all active jobs.

Example Execution Flow
🔹 Add Jobs: A → B → C
🔹 Execute Jobs: A → B → C → A → B → C
🔹 Delete Job B: A → C → A → C

Output:
![image](https://github.com/user-attachments/assets/dbbba57d-f63f-4734-ba22-fa5570847ab3)


Installation & Usage:

Clone the repository:
git clone https://github.com/Ari-147/Circular-Linked-List-Scheduler.git
cd Circular-Linked-List-Scheduler

Compile and Run the Program:
g++ job_scheduler.cpp -o scheduler
./scheduler

Advantages & Disadvantages
✅ Advantages:
Efficient memory usage – No fixed-size constraints.
Fair scheduling – Jobs execute cyclically.
Dynamic job management – Add and remove jobs anytime.

❌ Disadvantages:
More complex than arrays due to pointer management.
Risk of infinite loops if not handled correctly.

Visual Representation
📌 Diagram Explaining Circular Linked List Execution

![image](https://github.com/user-attachments/assets/5eb8e7ed-2648-4f76-86d8-d03597cdb8c9)
