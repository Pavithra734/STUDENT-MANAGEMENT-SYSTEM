# STUDENT-MANAGEMENT-SYSTEM
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Structure for Student Details
struct student {
    char name[30];
    int roll_no;
    int age;
    float marks;
};

int main() {
    struct student students[100];
    int count = 0, choice, i;
    int search_roll;

    while (1) {
        printf("\n\n*###### STUDENT MANAGEMENT SYSTEM #####*\n");
        printf("1. Add Student Information\n");
        printf("2. Display Student Information\n");
        printf("3. Search Student by Roll Number\n");
        printf("4. Display Total Number of Students\n");
        printf("5. Exit\n");

        printf("\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter Student Name: ");
                scanf("%s", students[count].name);
                printf("Enter Roll Number: ");
                scanf("%d", &students[count].roll_no);
                printf("Enter Age: ");
                scanf("%d", &students[count].age);
                printf("Enter Marks: ");
                scanf("%f", &students[count].marks);
                count++;
                break;

            case 2:
                printf("\nStudent Details:\n");
                for (i = 0; i < count; i++) {
                    printf("Name: %s, Roll No: %d, Age: %d, Marks: %.2f\n", 
                           students[i].name, students[i].roll_no, students[i].age, students[i].marks);
                }
                break;

            case 3:
                printf("Enter Roll Number to Search: ");
                scanf("%d", &search_roll);
                for (i = 0; i < count; i++) {
                    if (students[i].roll_no == search_roll) {
                        printf("\nStudent Found: Name: %s, Roll No: %d, Age: %d, Marks: %.2f\n", 
                               students[i].name, students[i].roll_no, students[i].age, students[i].marks);
                        break;
                    }
                }
                if (i == count) {
                    printf("Student Not Found!\n");
                }
                break;

            case 4:
                printf("Total Number of Students: %d\n", count);
                break;

            case 5:
                exit(0);

            default:
                printf("Invalid Choice! Please try again.\n");
        }
    }
    return 0;
}
