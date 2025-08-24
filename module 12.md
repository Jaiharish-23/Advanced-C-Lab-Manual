

### EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void display() {
    struct Node* p = head; 
    printf("Stack elements are:\n");
    while (p != NULL) {
        printf("%d\n", p->data);  
        p = p->next;            
    }
}

int main() {
    push(23);
    push(24);
    push(33);
    push(33);
    display();

    return 0;
}
```

Output:


<img width="916" height="388" alt="image" src="https://github.com/user-attachments/assets/478e2a1e-1e7c-4fd8-8729-1f98c98ff645" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



### EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

struct Node* head = NULL;

void push(char str) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = str;
    newNode->next = head;
    head = newNode;
}

void pop() {
    if (head == NULL) {
        printf("Underflow.\n");
    } else {
        struct Node* temp = head; 
        printf("Popped element: %c\n", temp->data); 
        head = head->next; 
        free(temp); 
    }
}

void display() {
    if (head == NULL) {
        printf("No element to display.\n");
        return;
    }
    struct Node* p = head;
    printf("Stack elements:\n");
    while (p != NULL) {
        printf("%c\n", p->data);
        p = p->next;
    }
}

int main() {
    push('J');
    push('A');
    push('I');
    printf("Stack before popping:\n");
    display();
    pop();
    printf("Stack after popping:\n");
    display();
    pop();
    pop();
    pop();

    return 0;
}

```

Output:

<img width="1192" height="466" alt="image" src="https://github.com/user-attachments/assets/930b9a4e-1025-4305-9103-cce2fb883cd3" />



Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
### EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(char str) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = str;
    newNode->next = NULL;
    if (rear == NULL) {
        front = rear = newNode; 
    } else {
        rear->next = newNode; 
        rear = newNode;       
    }
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    struct Node* temp = front; 
    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%c\n", temp->data); 
        temp = temp->next;          
    }
}

int main() {
    printf("Implementation of queue using linked list\n");
    enqueue('j');
    enqueue('a');
    enqueue('i');

    display();

    return 0;
}
```


Output:

<img width="1002" height="305" alt="image" src="https://github.com/user-attachments/assets/dc8e1ff5-fb9a-4a9e-a56f-b3632236f379" />

Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
### EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(char str) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    
    newNode->data = str;
    newNode->next = NULL;
    
    if (rear == NULL) {
        front = rear = newNode; 
    } else {
        rear->next = newNode;  
        rear = newNode;       
    }
    printf("%c is inserted.\n", str);
}

void display() {
    if (front == NULL) {
        printf("No element in the Queue\n");
        return;
    }

    struct Node* temp = front; 
    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%c\n", temp->data); 
        temp = temp->next;         
    }
}

int main() {
    enqueue('j');
    enqueue('a');
    enqueue('i');

    display();

    return 0;
}
```

Output:


 <img width="904" height="382" alt="image" src="https://github.com/user-attachments/assets/04de92ca-c08c-497f-b5ed-25775af37ef0" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



### EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(char str) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = str;
    newNode->next = NULL;

    if (rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

int peek() {
    if (front == NULL) {
        printf("No element in the Queue.\n");
    }
    printf("Front element of the queue is: %c\n", front->data);
    
}

int main() {
    enqueue('J');
    enqueue('A');
    enqueue('I');
    peek();
}
```

Output:

<img width="872" height="269" alt="image" src="https://github.com/user-attachments/assets/caa1490b-7d5f-4da5-81c2-e4dfb180dd40" />



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


