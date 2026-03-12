# Advanced-C-Lab-Manual

## EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim: To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
```
Declare structure eligible with age (integer) and n (character array)
Declare variable e of type eligible
Input age and name using scanf, store in e
If e.age <= 6
Print "Vaccine Eligibility: No" Else
Print "Vaccine Eligibility: Yes"
Print details (e.age, e.n)
Return 0
```
Program:
```
#include <stdio.h>

struct Person
{
    char name[50];
    int age;
};

int main()
{
    struct Person p[5];
    int i, n;

    printf("Enter number of persons: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++)
    {
        printf("\nEnter name: ");
        scanf("%s", p[i].name);

        printf("Enter age: ");
        scanf("%d", &p[i].age);
    }

    printf("\nVaccine Eligibility List:\n");

    for(i = 0; i < n; i++)
    {
        if(p[i].age > 6)
        {
            printf("%s is Eligible for Vaccine\n", p[i].name);
        }
        else
        {
            printf("%s is Not Eligible for Vaccine\n", p[i].name);
        }
    }

    return 0;
}
```
Output:

<img width="510" height="484" alt="image" src="https://github.com/user-attachments/assets/897bde4d-cfd6-4029-9054-7ecaa10fc7c4" />


Result: Thus, the program is verified successfully.


## EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION 

Aim: To write a C program for passing structure as function and returning a structure from a function

Algorithm:
```
Define structure numbers with members a and b.
Declare variable n of type numbers.
Prompt the user to enter values for a and b.
Input values for a and b into n using scanf.
Call the add function with n as an argument.
Print the result returned by the add function.
Return 0
```
Program:
```
#include <stdio.h>

struct Student
{
    int roll;
    float marks;
};

// Function declaration
struct Student getData(struct Student s);

int main()
{
    struct Student s1, s2;

    printf("Enter Roll Number: ");
    scanf("%d", &s1.roll);

    printf("Enter Marks: ");
    scanf("%f", &s1.marks);

    // Passing structure to function and receiving structure
    s2 = getData(s1);

    printf("\nStudent Details:\n");
    printf("Roll Number: %d\n", s2.roll);
    printf("Marks: %.2f\n", s2.marks);

    return 0;
}

// Function definition
struct Student getData(struct Student s)
{
    printf("\nInside Function\n");
    printf("Roll Number: %d\n", s.roll);
    printf("Marks: %.2f\n", s.marks);

    return s;   // returning structure
}
```

Output:

<img width="432" height="476" alt="image" src="https://github.com/user-attachments/assets/a45785f6-1388-426a-8ee0-b9dba7f7c9dc" />


Result: Thus, the program is verified successfully


## EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim: To write a C program to read a file name from user

Algorithm:
```
Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare a character array name to store the file name.
Prompt the user to enter a file name. Use scanf to input the file name into the name array.
Print a message indicating that the file with the specified name has been created successfully.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use fclose to close the file.
Print a message indicating that the file has been closed.
End the main function.
Return 0 to indicate successful program execution.
```
Program:
```
#include <stdio.h>

int main()
{
    char filename[100];

    printf("Enter the file name: ");
    scanf("%s", filename);

    printf("The file name entered is: %s\n", filename);

    return 0;
}
```
Output:

<img width="469" height="285" alt="Screenshot 2026-03-12 083421" src="https://github.com/user-attachments/assets/781d4a2a-8d42-4b65-8f08-b8ac6ac4ef7d" />


Result: Thus, the program is verified successfully


## EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE 
Aim: To write a C program to read, a file and insert text in that file 

Algorithm:
```
Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use a loop to input strings from the user and write them to the file using fputs.
Use fclose to close the file.
Print a message indicating that data has been added successfully.
End the main function.
Return 0 to indicate successful program execution.
```
Program:
```
#include <stdio.h>

int main()
{
    FILE *fp;
    char filename[50], text[200], ch;

    printf("Enter the file name: ");
    scanf("%s", filename);

    // Open file in append mode to insert text
    fp = fopen(filename, "a");

    if(fp == NULL)
    {
        printf("File cannot be opened.\n");
        return 0;
    }

    printf("Enter text to insert into the file:\n");
    getchar(); // clear newline
    fgets(text, sizeof(text), stdin);

    fputs(text, fp);   // write text to file
    fclose(fp);

    // Reopen file to read content
    fp = fopen(filename, "r");

    printf("\nContents of the file:\n");
    while((ch = fgetc(fp)) != EOF)
    {
        printf("%c", ch);
    }

    fclose(fp);
    return 0;
}
```

Output:

<img width="419" height="182" alt="image" src="https://github.com/user-attachments/assets/b4be78a7-ef05-4f3a-b3a8-d7ab6922ad9d" />


Result: Thus, the program is verified successfully


## Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim: The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm: 
```
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Subject
{
    char name[50];
    int marks;
};

int main()
{
    int n, i;
    struct Subject *s;

    printf("Enter number of subjects: ");
    scanf("%d", &n);

    // Dynamic memory allocation
    s = (struct Subject *)malloc(n * sizeof(struct Subject));

    if(s == NULL)
    {
        printf("Memory allocation failed\n");
        return 0;
    }

    // Input subject details
    for(i = 0; i < n; i++)
    {
        printf("\nEnter subject name: ");
        scanf("%s", s[i].name);

        printf("Enter marks: ");
        scanf("%d", &s[i].marks);
    }

    // Display subject details
    printf("\nSubject Details:\n");
    for(i = 0; i < n; i++)
    {
        printf("Subject: %s\n", s[i].name);
        printf("Marks: %d\n", s[i].marks);
    }

    // Free allocated memory
    free(s);

    return 0;
}
```
Output:

<img width="516" height="544" alt="image" src="https://github.com/user-attachments/assets/cfb20927-59e7-4f4c-a766-4a6f83510091" />


Result: Thus, the program is verified successfully
