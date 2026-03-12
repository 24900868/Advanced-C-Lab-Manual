## EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER 

Aim: To write a C program to create a function to find the greatest number

Algorithm:
```
Include the necessary header #include <stdio.h>.
Use a series of if and else if statements to compare the values and return the maximum among them.
Declare variables n1, n2, n3, n4, and greater to store user input and the result.
Use scanf to take four integers as input.
Call the max_of_four function with the input integers and store the result in the greater variable
```
Program: 
```
#include <stdio.h>

int greatest(int a, int b, int c) {
    int max;

    max = a;

    if(b > max)
        max = b;

    if(c > max)
        max = c;

    return max;
}

int main() {
    int x, y, z, result;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &x, &y, &z);

    result = greatest(x, y, z);

    printf("Greatest number = %d", result);

    return 0;
}
```
Output:

<img width="1383" height="848" alt="image" src="https://github.com/user-attachments/assets/3b650e2a-2cd1-4baf-ade3-4e672931f0ff" />


Result: Thus, the program that create a function to find the greatest number is verified successfully.


## EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND XOR COMPARISONS 

Aim: To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
```
Define a function calculate_the_max that takes two integers n and k as parameters.
Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
Declare variables n and k to store user input.
Use scanf to take two integers as input.
Call the calculate_the_max function with input values.
```
Program:
```
#include <stdio.h>

int main() {
    int max_and = 0, max_or = 0, max_xor = 0;
    int n, k;

    printf("Enter value of n and k: ");
    scanf("%d %d", &n, &k);

    for(int i = 1; i <= n; i++) {
        for(int j = i + 1; j <= n; j++) {

            if((i & j) < k && (i & j) > max_and)
                max_and = i & j;

            if((i | j) < k && (i | j) > max_or)
                max_or = i | j;

            if((i ^ j) < k && (i ^ j) > max_xor)
                max_xor = i ^ j;
        }
    }

    printf("Maximum AND value = %d\n", max_and);
    printf("Maximum OR value = %d\n", max_or);
    printf("Maximum XOR value = %d\n", max_xor);

    return 0;
}
```

Output: 

<img width="1429" height="899" alt="image" src="https://github.com/user-attachments/assets/fac5ebe1-2e21-4e72-be50-333ee96f5de7" />


Result: Thus, the program to print the maximum values for the AND, OR and XOR comparisons is verified successfully.


## EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS 

Aim: To write a C program to write the logic for the requests

Algorithm:
```
Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
Use scanf to take two integers as input for the number of shelves and queries.
Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
Declare variables k and c to keep track of the book index and the total number of books.
Use a for loop to iterate over the queries.
```
Program: 
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int q;
    scanf("%d", &q);

    int *arr = NULL;
    int size = 0;

    while(q--) {
        int type;
        scanf("%d", &type);

        if(type == 1) {
            int x;
            scanf("%d", &x);

            size++;
            arr = realloc(arr, size * sizeof(int));
            arr[size - 1] = x;
        }
        else if(type == 2) {
            int idx;
            scanf("%d", &idx);

            for(int i = idx; i < size - 1; i++) {
                arr[i] = arr[i + 1];
            }

            size--;
            arr = realloc(arr, size * sizeof(int));
        }
        else if(type == 3) {
            int idx;
            scanf("%d", &idx);
            printf("%d\n", arr[idx]);
        }
    }

    free(arr);
    return 0;
}
```
Output:

<img width="1233" height="749" alt="image" src="https://github.com/user-attachments/assets/2abda62d-1c70-4695-aea2-30718dca647a" />


Result: Thus, the program to write the logic for the requests is verified successfully.

## EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY. 

Aim: To write a C program print the sum of the integers in the array.

Algorithm:
```
Declare a variable n to store the number of integers.
Use scanf to take an integer n as input.
Declare an array a of size n to store the integers.
Declare a variable sum and initialize it to zero.
Use a for loop to iterate n times:
Use scanf to input each integer and add it to the sum.
Print the final sum using printf.
```
Program: 
```
#include <stdio.h>

int main() {
    int arr[100], n, i, sum = 0;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter the elements:\n");
    for(i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    for(i = 0; i < n; i++) {
        sum = sum + arr[i];
    }

    printf("Sum of array elements = %d", sum);

    return 0;
}
```
Output:

<img width="1312" height="650" alt="image" src="https://github.com/user-attachments/assets/208d2db3-e4dd-4f18-82c9-544443f1faee" />


Result: Thus, the program prints the sum of the integers in the array is verified successfully.

## EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

Aim: To write a C program that counts the number of words in a given sentence.

Algorithm:
```
Input the sentence: Take a sentence from the user.
Initialize a counter variable: This will keep track of the number of words.
Process each character of the sentence: o Iterate through the sentence, checking each character. o If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
Display the result: After processing the sentence, output the total word count.
```
Program: 
```
#include <stdio.h>

int main() {
    char str[200];
    int i, count = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    for(i = 0; str[i] != '\0'; i++) {
        if(str[i] == ' ' || str[i] == '\n') {
            count++;
        }
    }

    printf("Number of words = %d", count + 1);

    return 0;
}
```
Output: 

<img width="1351" height="615" alt="image" src="https://github.com/user-attachments/assets/82afec36-1c0d-4bcb-b95c-74ad868a5e06" />


Result:

Thus, the program that counts the number of words in a given sentence is verified successfully.
