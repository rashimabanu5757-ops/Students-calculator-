# Students-calculator-
To calculate mark
#include <stdio.h>

// Define structure for Student
struct Student {
    int rollNo;
    char name[50];
    int marks[5];   // Marks for 5 subjects
    int total;
    float average;
};

int main() {
    struct Student s;
    int i;

    // Input student details
    printf("Enter Roll Number: ");
    scanf("%d", &s.rollNo);

    printf("Enter Name: ");
    scanf("%s", s.name);

    s.total = 0;

    // Input marks
    printf("Enter marks in 5 subjects:\n");
    for (i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%d", &s.marks[i]);
        s.total += s.marks[i];
    }

    // Calculate average
    s.average = s.total / 5.0;

    // Display results
    printf("\n---- Student Marksheet ----\n");
    printf("Roll No   : %d\n", s.rollNo);
    printf("Name      : %s\n", s.name);
    printf("Total     : %d\n", s.total);
    printf("Average   : %.2f\n", s.average);

    if (s.average >= 50)
        printf("Result    : PASS\n");
    else
        printf("Result    : FAIL\n");

    return 0;
}
