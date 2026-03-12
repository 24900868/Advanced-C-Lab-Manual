## EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST. 

Aim: To write a C program to search a given element in the given linked list.

Algorithm:
```
Define the structure for a node in a linked list.
Define the search function to find a specific character in the linked list.
Initialize the head of the linked list as needed.
Call the search function and perform other linked list operations as needed.
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

int search(struct node *head, int key) {
    int position = 1;
    struct node *temp = head;

    while(temp != NULL) {
        if(temp->data == key)
            return position;
        temp = temp->next;
        position++;
    }

    return -1;
}

int main() {
    struct node *head = NULL, *newnode, *temp;
    int n, value, key, pos;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(int i = 0; i < n; i++) {
        newnode = (struct node*)malloc(sizeof(struct node));

        printf("Enter value: ");
        scanf("%d", &value);

        newnode->data = value;
        newnode->next = NULL;

        if(head == NULL) {
            head = newnode;
            temp = head;
        } else {
            temp->next = newnode;
            temp = newnode;
        }
    }

    printf("Enter element to search: ");
    scanf("%d", &key);

    pos = search(head, key);

    if(pos == -1)
        printf("Element not found");
    else
        printf("Element found at position %d", pos);

    return 0;
}
```
Output:

<img width="1287" height="658" alt="image" src="https://github.com/user-attachments/assets/ef969063-29a7-4611-887b-8adc7807f982" />


Result: Thus, the program to search a given element in the given linked list is verified successfully.


## EXP NO:17 PROGRAM TO INSERT A NODE IN A LINKED LIST. 

Aim: To write a C program to insert a node in a linked list. 

Algorithm:
```
Define the structure for a node in a linked list
Define the insert function to insert a new node with character data at the end of the linked list.
Initialize the head of the linked list as needed.
Call the insert function and perform other linked list operations as needed.
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

int main() {
    struct node *head = NULL, *temp, *newnode;
    int n, i, value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        newnode = (struct node*)malloc(sizeof(struct node));

        printf("Enter value: ");
        scanf("%d", &value);

        newnode->data = value;
        newnode->next = NULL;

        if(head == NULL) {
            head = newnode;
            temp = head;
        }
        else {
            temp->next = newnode;
            temp = newnode;
        }
    }

    // Insert new node
    newnode = (struct node*)malloc(sizeof(struct node));
    printf("Enter value to insert: ");
    scanf("%d", &value);

    newnode->data = value;
    newnode->next = head;
    head = newnode;

    // Display linked list
    printf("Linked list after insertion:\n");
    temp = head;
    while(temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    return 0;
}
```
Output:

<img width="1328" height="831" alt="image" src="https://github.com/user-attachments/assets/bee25145-79c1-4d86-bffb-38740b561f84" />


Result: Thus, the program to insert a node in a linked list is verified successfully.


## EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST 

Aim: To write a C program to traverse a doubly linked list.

Algorithm:
```
Initialize a temporary pointer (temp) to the head of the list.
Use a while loop to traverse the list until the end (temp == NULL) is reached.
Inside the loop, print the data of the current node.
Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *prev;
    struct node *next;
};

int main() {
    struct node *head = NULL, *temp, *newnode;
    int n, value, i;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        newnode = (struct node*)malloc(sizeof(struct node));

        printf("Enter value: ");
        scanf("%d", &value);

        newnode->data = value;
        newnode->prev = NULL;
        newnode->next = NULL;

        if(head == NULL) {
            head = newnode;
            temp = head;
        } else {
            temp->next = newnode;
            newnode->prev = temp;
            temp = newnode;
        }
    }

    printf("Traversing the doubly linked list:\n");
    temp = head;
    while(temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    return 0;
}
```

Output:

<img width="1265" height="476" alt="image" src="https://github.com/user-attachments/assets/98fc6e7f-3376-40a8-8736-5c7b39cfcf90" />


Result: Thus, the program to traverse a doubly linked list is verified successfully.


## EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST 

Aim: To write a C program to insert an element in doubly linked list

Algorithm:
```
Create a new node (newNode) and allocate memory for it.
Set the data of the new node to the provided value.
If the list is empty, set the new node as the head.
If the list is not empty, traverse the list to find the last node.
Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *prev;
    struct node *next;
};

int main() {
    struct node *head = NULL, *temp, *newnode;
    int n, i, value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        newnode = (struct node*)malloc(sizeof(struct node));

        printf("Enter value: ");
        scanf("%d", &value);

        newnode->data = value;
        newnode->prev = NULL;
        newnode->next = NULL;

        if(head == NULL) {
            head = newnode;
            temp = head;
        } 
        else {
            temp->next = newnode;
            newnode->prev = temp;
            temp = newnode;
        }
    }

    // Insert new node at beginning
    newnode = (struct node*)malloc(sizeof(struct node));

    printf("Enter value to insert: ");
    scanf("%d", &value);

    newnode->data = value;
    newnode->prev = NULL;
    newnode->next = head;

    if(head != NULL)
        head->prev = newnode;

    head = newnode;

    // Display list
    printf("Doubly Linked List after insertion:\n");
    temp = head;
    while(temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    return 0;
}
```
Output:

<img width="1441" height="759" alt="image" src="https://github.com/user-attachments/assets/92cff3f9-fa36-4bee-b91f-60be1edddad5" />


Result: Thus, the program to insert an element in doubly linked list is verified successfully.


## EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim: To write a C function that deletes a given element from a linked list.

Algorithm:
```
Check if the Linked List is Empty: o If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
Traverse the Linked List: o Start from the head node and iterate through the list to find the node that contains the given element (data).
Handle Deletion of the First Node: o If the element to be deleted is found in the head node:  Update the head of the linked list to point to the next node (i.e., head = head->next).  Free the memory allocated to the node to be deleted.  Exit the function.
Traverse and Delete from the Middle or End: o If the element is not in the head node, continue traversing the list by checking each node’s next pointer. o When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next). o Free the memory allocated to the node to be deleted.
Handle the Case when the Element is Not Found: o If the element is not found in any node, print a message indicating the element is not present in the list.
End the Function.
```
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

struct node* deleteElement(struct node *head, int key) {
    struct node *temp = head, *prev = NULL;

    // If head node holds the element
    if(temp != NULL && temp->data == key) {
        head = temp->next;
        free(temp);
        return head;
    }

    // Search for the element
    while(temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    // If element not found
    if(temp == NULL) {
        printf("Element not found\n");
        return head;
    }

    // Unlink node and delete
    prev->next = temp->next;
    free(temp);

    return head;
}

void display(struct node *head) {
    struct node *temp = head;
    while(temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {
    struct node *head = NULL, *temp, *newnode;
    int n, value, key;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(int i = 0; i < n; i++) {
        newnode = (struct node*)malloc(sizeof(struct node));

        printf("Enter value: ");
        scanf("%d", &value);

        newnode->data = value;
        newnode->next = NULL;

        if(head == NULL) {
            head = newnode;
            temp = head;
        } else {
            temp->next = newnode;
            temp = newnode;
        }
    }

    printf("Enter element to delete: ");
    scanf("%d", &key);

    head = deleteElement(head, key);

    printf("Linked list after deletion:\n");
    display(head);

    return 0;
}
```
Output:

<img width="1288" height="526" alt="image" src="https://github.com/user-attachments/assets/3941b668-b3c2-416c-abf1-244151e74900" />


Result: Thus, the function that deletes a given element from a linked list is verified successfully.
