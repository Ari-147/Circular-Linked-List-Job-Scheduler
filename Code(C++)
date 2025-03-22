#include <iostream>
using namespace std;

// Structure for a Job Node
struct JobNode {
    int job_id;
    string job_name;
    int execution_time;
    JobNode* next;
};

// Structure for the Circular Linked List
struct JobScheduler {
    JobNode* head;  
};

// Function to initialize the scheduler
void initScheduler(JobScheduler &scheduler) {
    scheduler.head = nullptr;
}

// Function to add a job
void addJob(JobScheduler &scheduler, int job_id, string job_name, int execution_time) {
    JobNode* newJob = new JobNode{job_id, job_name, execution_time, nullptr};

    if (!scheduler.head) {
        scheduler.head = newJob;
        newJob->next = newJob;  
    } else {
        JobNode* temp = scheduler.head;
        while (temp->next != scheduler.head) {
            temp = temp->next;
        }
        temp->next = newJob;
        newJob->next = scheduler.head;
    }
}

// Function to delete a job
void deleteJob(JobScheduler &scheduler, int job_id) {
    if (!scheduler.head) {
        cout << "No jobs to delete.\n";
        return;
    }

    JobNode* current = scheduler.head;
    JobNode* prev = nullptr;

    do {
        if (current->job_id == job_id) {
            if (prev) {
                prev->next = current->next;
            } else {
                JobNode* temp = scheduler.head;
                while (temp->next != scheduler.head) {
                    temp = temp->next;
                }
                temp->next = scheduler.head->next;
                scheduler.head = scheduler.head->next;
            }
            delete current;
            return;
        }
        prev = current;
        current = current->next;
    } while (current != scheduler.head);

    cout << "Job ID not found.\n";
}

// Function to execute jobs in a circular manner
void executeJobs(JobScheduler &scheduler, int cycles = 1) {
    if (!scheduler.head) {
        cout << "No jobs in the queue.\n";
        return;
    }

    JobNode* current = scheduler.head;
    for (int i = 0; i < cycles; i++) {
        do {
            cout << "Executing Job ID: " << current->job_id
                 << ", Name: " << current->job_name
                 << ", Time: " << current->execution_time << " seconds" << endl;
            current = current->next;
        } while (current != scheduler.head);
    }
}

// Function to display jobs in the queue
void displayJobs(JobScheduler &scheduler) {
    if (!scheduler.head) {
        cout << "No jobs in the queue.\n";
        return;
    }

    JobNode* current = scheduler.head;
    do {
        cout << "Job ID: " << current->job_id
             << ", Name: " << current->job_name
             << ", Time: " << current->execution_time << " seconds" << endl;
        current = current->next;
    } while (current != scheduler.head);
}

// Main function to test the implementation
int main() {
    JobScheduler scheduler;
    initScheduler(scheduler);

    addJob(scheduler, 1, "Data Backup", 5);
    addJob(scheduler, 2, "Image Rendring", 3);
    addJob(scheduler, 3, "System Health Check", 7);

    cout << "Job Queue:\n";
    displayJobs(scheduler);

    cout << "\nExecuting Jobs:\n";
    executeJobs(scheduler, 2);

    cout << "\nDeleting Job 2:\n";
    deleteJob(scheduler, 2);
    displayJobs(scheduler);

    return 0;
}
