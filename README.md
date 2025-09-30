#include <stdio.h>

// Structure definition
struct Student {
    int rollNo;
    char name[50];
    int marks[5];     // 5 subjects
    int total;
    float average;
};

int main() {
    int i, j, n;
    
    printf("Enter number of students: ");
    scanf("%d", &n);

    struct Student s[n];

    for (i = 0; i < n; i++) {
        s[i].total = 0;
        
        printf("\nEnter details of student %d:\n", i + 1);
        printf("Roll No: ");
        scanf("%d", &s[i].rollNo);
        printf("Name: ");
        scanf("%s", s[i].name);

        printf("Enter marks of 5 subjects:\n");
        for (j = 0; j < 5; j++) {
            scanf("%d", &s[i].marks[j]);
            s[i].total += s[i].marks[j];
        }
        s[i].average = s[i].total / 5.0;
    }

    // Display result
    printf("\n--- Student Marks Report ---\n");
    for (i = 0; i < n; i++) {
        printf("\nRoll No: %d\n", s[i].rollNo);
        printf("Name: %s\n", s[i].name);
        printf("Total Marks: %d\n", s[i].total);
        printf("Average: %.2f\n", s[i].average);
    }

    return 0;
}

