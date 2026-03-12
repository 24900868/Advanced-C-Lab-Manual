## EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim: To write a C program to display stack elements using an array. 

Algorithm:
```
Include Necessary Header Files
Declare Global Variables
Define the Display Function
Main Function (or Other Relevant Code)
Initialize the stack and top as needed.
Perform stack operations (push, pop, etc.).
Use the display function to visualize the stack's contents
```
Program:
```
#include <stdio.h>

#define MAX 5

int stack[MAX];
int top = -1;

void push(int value) {
    if(top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
    }
}

void display() {
    if(top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements are:\n");
        for(int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    push(40);

    display();

    return 0;
}
```
Output:

<img width="1276" height="777" alt="image" src="https://github.com/user-attachments/assets/dbd76834-0e62-4ded-b785-130a15d33e86" />


Result: Thus, the program to display stack elements using an array is verified successfully.


## EXP NO:12 PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY. 

Aim: To create a C program to push the given element in to a stack using array. 

Algorithm:
```
Declare global variables for the stack size, top index, and the stack itself.
Define the push function to add a floating-point number to the stack.
Initialize the stack size, top index, and the stack itself.
Call the push function as needed.
```
Program:
```
#include <stdio.h>

#define MAX 5

int stack[MAX];
int top = -1;

void push(int value) {
    if(top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
        printf("Element %d pushed into stack\n", value);
    }
}

int main() {
    int element;

    printf("Enter element to push: ");
    scanf("%d", &element);

    push(element);

    return 0;
}
```
Output:

<img width="1307" height="815" alt="image" src="https://github.com/user-attachments/assets/5a4005f3-bb64-458d-8a46-f48d94d104f3" />


Result: Thus, the program to push the given element in to a stack using array is verified successfully


## EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY. 

Aim: To write a C program to display queue elements using array

Algorithm:
```
Declare global variables for the queue, rear, front, and iteration.
Define the display function to print the elements of the queue.
Initialize the queue, rear, and front as needed.
Call the display function and perform other queue operations as needed.
```
Program:
```
#include <stdio.h>

#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int value) {
    if(rear == MAX - 1) {
        printf("Queue Overflow\n");
    } else {
        if(front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
    }
}

void display() {
    if(front == -1) {
        printf("Queue is empty\n");
    } else {
        printf("Queue elements are:\n");
        for(int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
    }
}

int main() {

    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();

    return 0;
}
```
Output:

<img width="1207" height="839" alt="image" src="https://github.com/user-attachments/assets/84b0ccf8-5922-4d42-876b-6a6ebaaf79cf" />


Result: Thus, the program to display queue elements using array is verified successfully.


## EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY. 

Aim: To write a C program to insert elements in queue using array.

Algorithm:
```
Declare global variables for the size, rear, front, and the queue itself.
Define the enqueue function to add a float to the queue.
Initialize the rear, front, and size of the queue as needed.
Call the enqueue function as needed.
```
Program:
```
#include <stdio.h>

#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
    } 
    else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("Inserted element: %d\n", value);
    }
}

int main() {
    int element;

    printf("Enter element to insert into queue: ");
    scanf("%d", &element);

    enqueue(element);

    return 0;
}
```
Output:

<img width="1485" height="901" alt="image" src="https://github.com/user-attachments/assets/b8cb4873-3e92-4967-ae76-85ec10a5ebec" />


Result: Thus, the program to insert elements in queue using array is verified successfully.


## EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

Aim: To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:
```
Check if the Queue is Empty o If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
Delete the Front Element o If the queue is not empty, the element at the front index is deleted. o Increment the front pointer by 1 to remove the element and point to the next element in the queue.
Check if the Queue Becomes Empty After Deletion: o After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
End the Function.
```
Program:
```
#include <stdio.h>

#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int value) {
    if(rear == MAX - 1) {
        printf("Queue Overflow\n");
    } else {
        if(front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
    }
}

void dequeue() {
    if(front == -1 || front > rear) {
        printf("Queue Underflow\n");
    } else {
        printf("Deleted element: %d\n", queue[front]);
        front++;
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    dequeue();

    return 0;
}
```
Output:

<img width="1284" height="782" alt="image" src="https://github.com/user-attachments/assets/95a61193-cdcc-4fcf-97a1-899cbe142b1f" />


Result: Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
