### EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

struct Node* createNode(char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

void search(struct Node* head, char target) {
    int position = 0;
    struct Node* current = head;

    while (current != NULL) {
        position++;
        if (current->data == target) {
            printf("Element '%c' found at position %d.\n", target, position);
            return;
        }
        current = current->next;
    }
    printf("Element '%c' not found in the linked list.\n", target);
}

int main() {
    struct Node* head = createNode('A');
    head->next = createNode('B');
    head->next->next = createNode('C');
    head->next->next->next = createNode('D');

    search(head, 'C');
    search(head, 'E');

    return 0;
}
```

Output:

<img width="1185" height="285" alt="image" src="https://github.com/user-attachments/assets/b2db2f5f-2e7d-492c-8478-e7d724e0adbc" />




Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

struct Node* createNode(char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

void insert(struct Node** head, char value) {
    struct Node* newNode = createNode(value);

    if (*head == NULL) {
        *head = newNode;
    } else {
        struct Node* temp = *head;
        while (temp->next != NULL) { 
            temp = temp->next;
        }
        temp->next = newNode;
    }
}

void display(struct Node* head) {
    struct Node* temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    insert(&head, 'J');
    insert(&head, 'a');
    insert(&head, 'i');
    insert(&head, 'h');

    display(head);

    return 0;
}
```

Output:

<img width="761" height="200" alt="image" src="https://github.com/user-attachments/assets/08b49b7f-e921-4a3d-9201-9b41e80ad924" />


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;
    return newNode;
}

void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Element In The Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = createNode(100);
    struct Node* second = createNode(200);
    struct Node* third = createNode(300);

    head->next = second;
    second->prev = head;
    second->next = third;
    third->prev = second;

    traverse(head);

    return 0;
}
```

Output:

<img width="1223" height="253" alt="image" src="https://github.com/user-attachments/assets/126105b7-05c3-440c-b221-caddf07b7463" />



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;
    return newNode;
}

void insertEnd(struct Node** head, int value) {
    struct Node* newNode = createNode(value);
    
    if (*head == NULL) {
        *head = newNode;
    } else {
        struct Node* temp = *head;
        while (temp->next != NULL) { 
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->prev = temp;
    }
    printf("Element %d had been inserted\n",value);
}

void display(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    insertEnd(&head, 40);

    display(head);

    return 0;
}
```

Output:

<img width="838" height="272" alt="image" src="https://github.com/user-attachments/assets/a58f5ab4-411e-4338-9492-69f2ef6ca7a6" />



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    float data;
    struct Node* next;
};

void deleteNode(struct Node** head, float target) {
    struct Node* temp = *head;
    struct Node* prev = NULL;

    if (*head == NULL) {
        printf("Linked list is empty.\n");
        return;
    }

    while (temp != NULL && temp->data != target) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element %.2f not found.\n", target);
        return;
    }

    if (temp == *head) {
        *head = temp->next;
    } else {
        prev->next = temp->next;
    }

    free(temp);
    printf("Element %.2f successfully deleted.\n", target);
}

void display(struct Node* head) {
    struct Node* temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%.2f -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL; 
    head = (struct Node*)malloc(sizeof(struct Node));
    head->data = 2.3;
    head->next = (struct Node*)malloc(sizeof(struct Node));
    head->next->data = 2.0;
    head->next->next = (struct Node*)malloc(sizeof(struct Node));
    head->next->next->data = 7.5;
    head->next->next->next = NULL;
    display(head);
    deleteNode(&head, 1.2);
    display(head);
    deleteNode(&head, 9.2);
    display(head);

    return 0;
}
```

Output:

<img width="966" height="294" alt="image" src="https://github.com/user-attachments/assets/aa5aa477-47f6-4a99-b5ef-5795a8ac8561" />






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





