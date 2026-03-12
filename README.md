## EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST. 

Aim: To write a C program to display stack elements using linked list.

Algorithm:
```
Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
Declare a global variable head representing the starting node of the linked list.
Define a function display to print the elements of the linked list.
Declare a pointer p and initialize it with the head of the linked list.
Use a while loop to traverse the linked list:
Print the data of the current node.
Move to the next node using the next pointer.
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

struct node *top = NULL;

void push(int value) {
    struct node *newnode;
    newnode = (struct node*)malloc(sizeof(struct node));
    
    newnode->data = value;
    newnode->next = top;
    top = newnode;
}

void display() {
    struct node *temp;

    if(top == NULL) {
        printf("Stack is empty\n");
        return;
    }

    temp = top;
    printf("Stack elements are:\n");

    while(temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {

    push(10);
    push(20);
    push(30);

    display();

    return 0;
}
```
Output:

<img width="1225" height="557" alt="image" src="https://github.com/user-attachments/assets/a9f025a9-3595-4875-a069-bd8749dfb294" />


Result: Thus, the program to display stack elements using linked list is verified successfully.

## EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST. 

Aim: To write a C program to pop an element from the given stack using liked list.

Algorithm:
```
Check for Empty Stack
If head is equal to NULL, Print "Stack is empty."
Else Proceed to the next step.
Set head to point to the next node in the stack.
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

struct node *top = NULL;

void push(int value) {
    struct node *newnode;
    newnode = (struct node*)malloc(sizeof(struct node));

    newnode->data = value;
    newnode->next = top;
    top = newnode;
}

void pop() {
    struct node *temp;

    if(top == NULL) {
        printf("Stack Underflow\n");
        return;
    }

    temp = top;
    printf("Popped element: %d\n", top->data);
    top = top->next;
    free(temp);
}

int main() {
    push(10);
    push(20);
    push(30);

    pop();

    return 0;
}
```
Output:

<img width="1196" height="556" alt="image" src="https://github.com/user-attachments/assets/93d99ff1-8ae1-4592-97dd-f57dbce9e968" />


Result: Thus, the program to pop an element from the given stack using liked list is verified successfully.

## EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST. 

Aim: To write a C program to display queue elements using linked list. 

Algorithm:
```
Check if Queue is Empty
Display Queue Elements
Print the data of the current node pointed to by front
Update front to point to the next node.
End the display function.
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

struct node *front = NULL;
struct node *rear = NULL;

void enqueue(int value) {
    struct node *newnode;
    newnode = (struct node*)malloc(sizeof(struct node));

    newnode->data = value;
    newnode->next = NULL;

    if(front == NULL) {
        front = rear = newnode;
    } else {
        rear->next = newnode;
        rear = newnode;
    }
}

void display() {
    struct node *temp;

    if(front == NULL) {
        printf("Queue is empty\n");
        return;
    }

    temp = front;
    printf("Queue elements are:\n");

    while(temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    return 0;
}
```
Output:

<img width="1188" height="755" alt="image" src="https://github.com/user-attachments/assets/3f891699-0791-4285-ad84-250cc34d9a1a" />


Result: Thus, the program to display queue elements using linked list is verified successfully.

## EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim: To write a C program to insert elements in queue using linked list

Algorithm:
```
Allocate Memory for New Node
Set Data and Next Pointer
Check if Queue is Empty
Set both front and rear to point to the new node p.
Set the next pointer of the current rear to point to the new node p.
End of Enqueue Operation
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

struct node *front = NULL;
struct node *rear = NULL;

void enqueue(int value) {
    struct node *newnode;
    newnode = (struct node*)malloc(sizeof(struct node));

    newnode->data = value;
    newnode->next = NULL;

    if(front == NULL) {
        front = rear = newnode;
    } 
    else {
        rear->next = newnode;
        rear = newnode;
    }

    printf("Inserted element: %d\n", value);
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

<img width="1307" height="750" alt="image" src="https://github.com/user-attachments/assets/6b754950-24d4-4829-9125-cb7da3ef9508" />


Result: Thus, the program to insert elements in queue using linked list is verified successfully.

## EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.

Aim: The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:
```
Check if the queue is empty: o If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
Access the front element: o If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

struct node *front = NULL;
struct node *rear = NULL;

void enqueue(int value) {
    struct node *newnode = (struct node*)malloc(sizeof(struct node));
    newnode->data = value;
    newnode->next = NULL;

    if(front == NULL) {
        front = rear = newnode;
    } else {
        rear->next = newnode;
        rear = newnode;
    }
}

void peek() {
    if(front == NULL) {
        printf("Queue is empty\n");
    } else {
        printf("Front element (Peek) = %d\n", front->data);
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    peek();

    return 0;
}
```
Output:

<img width="1272" height="721" alt="image" src="https://github.com/user-attachments/assets/3cbe2181-fecb-4309-ab60-ffa8d8e737fe" />


Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
