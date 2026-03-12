## EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER 

Aim: To write a C program print the lowercase English word corresponding to the number 

Algorithm:
```
Start
Initialize an integer variable n.
Input Validation
Switch Statement cases.
Case 5: Print "seventy one"
Case 6: Print "seventy two"
Case 13: Print "seventy three"
Case 13: Print "seventy nine"
Default: Print "Greater than 13"
Exit the program.
```
Program:
```
#include <stdio.h>

int main() {
    int num;

    printf("Enter a number (1-10): ");
    scanf("%d", &num);

    switch(num) {
        case 1: printf("one"); break;
        case 2: printf("two"); break;
        case 3: printf("three"); break;
        case 4: printf("four"); break;
        case 5: printf("five"); break;
        case 6: printf("six"); break;
        case 7: printf("seven"); break;
        case 8: printf("eight"); break;
        case 9: printf("nine"); break;
        case 10: printf("ten"); break;
        default: printf("number out of range");
    }

    return 0;
}
```

Output:

<img width="1346" height="762" alt="image" src="https://github.com/user-attachments/assets/3e96a64a-ffe2-4f42-bbbe-1776128e4101" />


Result: Thus, the program is verified successfully

## EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 . 

Aim: To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3. 

Algorithm:
```
Start
Declare char array a[50] outer loop for each digit from 0 to 3
Initialize counter c to 0
For each character in the string print count c for current digit, followed by a space
Increment h to move to the next digit
End
```
Program:
```
#include <stdio.h>

int main() {
    int i, digit;
    int freq[10] = {0};

    for(i = 0; i <= 3; i++) {
        digit = i;
        freq[digit]++;
    }

    for(i = 0; i < 10; i++) {
        printf("%d ", freq[i]);
    }

    return 0;
}
```
Output:

<img width="1210" height="571" alt="image" src="https://github.com/user-attachments/assets/24d0f3ce-7234-477f-8737-ba4bb0082be8" />


Result: Thus, the program is verified successfully

## EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER. 

Aim: To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
```
Start

Declare variables s (pointer to an array of strings) and n (number of strings)

Memory Allocation Dynamically allocate memory for s to store an array of strings

Input Read the number of strings n from the user Dynamically allocate memory for each string in s

Permutation Generation Loop

Memory Deallocation Free the memory allocated for each string in s Free the memory allocated for s

End
```
Program:
```
#include <stdio.h>
#include <string.h>

void swap(char *a, char *b) {
    char temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    char str[100];
    int i, j, len;

    printf("Enter a string: ");
    scanf("%s", str);

    len = strlen(str);

    // Sort the string in lexicographical order
    for(i = 0; i < len-1; i++) {
        for(j = i+1; j < len; j++) {
            if(str[i] > str[j]) {
                swap(&str[i], &str[j]);
            }
        }
    }

    do {
        printf("%s\n", str);

        // Find rightmost character smaller than next
        int k = len - 2;
        while(k >= 0 && str[k] >= str[k+1])
            k--;

        if(k < 0)
            break;

        // Find smallest character greater than str[k]
        int l = len - 1;
        while(str[l] <= str[k])
            l--;

        swap(&str[k], &str[l]);

        // Reverse from k+1 to end
        int start = k + 1, end = len - 1;
        while(start < end) {
            swap(&str[start], &str[end]);
            start++;
            end--;
        }

    } while(1);

    return 0;
}
```

Output:

<img width="502" height="516" alt="image" src="https://github.com/user-attachments/assets/09f6187d-1b38-45c1-b5db-554f34ef5fe2" />


Result: Thus, the program is verified successfully

## EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW. 

Aim: To write a C program to print a pattern of numbers from 1 to n as shown below. 

Algorithm:
```
Start
Declare integer variables n, i, j, min
Read the value of n from the user
Calculate the length of the side of the square matrix: len = n * 2 - 1
Matrix Generation Loop
Calculate min as the minimum distance to the borders
End
```
Program:
```
#include <stdio.h>

int main() {
    int n;
    scanf("%d", &n);

    int size = 2*n - 1;

    for(int i = 0; i < size; i++) {
        for(int j = 0; j < size; j++) {

            int top = i;
            int left = j;
            int right = size - j - 1;
            int bottom = size - i - 1;

            int min = top;

            if(left < min) min = left;
            if(right < min) min = right;
            if(bottom < min) min = bottom;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```

Output:

<img width="1222" height="878" alt="image" src="https://github.com/user-attachments/assets/b757dd0a-16a9-4bf3-9341-840a47be0929" />


Result: Thus, the program is verified successfully

## EXP NO:10 C PROGRAM TO FIND A SQUARE OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:
```
Start.
Define a function square() with no parameters. This function will return an integer value.
Inside the function: o Declare an integer variable to store the number. o Ask the user to input a number. o Calculate the square of the number (multiply the number by itself). o Return the squared value.
In the main function: o Call the square() function and display the result.
End.
```
Program:
```
#include <stdio.h>

int square();   // function declaration

int main() {
    int result;

    result = square();   // function call
    printf("Square of the number = %d", result);

    return 0;
}

int square() {
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    return num * num;   // returning square
}
```
Output:

<img width="1303" height="689" alt="image" src="https://github.com/user-attachments/assets/d413cca0-89af-470d-95ce-74d1941655de" />


Result: Thus, the program is verified successfully
