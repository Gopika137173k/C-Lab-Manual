EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>

#define MAX 5
int stack[MAX];
int top = -1;

void display() {
    if (top == -1) {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements: ");
    for (int i = 0; i <= top; i++) {
        printf("%d ", stack[i]);
    }
    printf("\n");
}

void push(int val) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
        return;
    }
    stack[++top] = val;
}

int main() {
    push(10);
    push(20);
    push(30);
    display();   // Output 1

    push(40);
    push(50);
    push(60);    // Should print Overflow
    display();   // Output 2

    return 0;
}
```
Output:
Output 1:
Stack elements: 10 20 30 
Output 2:
Stack Overflow
Stack elements: 10 20 30 40 50 
Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>

#define MAX 5
float stack[MAX];
int top = -1;

void push(float val) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
        return;
    }
    stack[++top] = val;
    printf("%.2f pushed into stack\n", val);
}

int main() {
    push(12.5);   // Output 1
    push(25.75);  // Output 2
    push(33.0);
    push(48.2);
    push(59.9);
    push(67.1);   // Stack Overflow

    return 0;
}
```
Output:
Output 1:
12.50 pushed into stack
Output 2:
25.75 pushed into stack
Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>

#define MAX 5
int queue[MAX];
int front = -1, rear = -1;

void display() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main() {
    // Initialize queue with some elements
    front = 0; rear = 2;
    queue[0] = 10;
    queue[1] = 20;
    queue[2] = 30;

    display();  // Output 1

    // Adding more elements
    rear = 4;
    queue[3] = 40;
    queue[4] = 50;

    display();  // Output 2

    return 0;
}
```

Output:
Output 1:
Queue elements: 10 20 30 
Output 2:
Queue elements: 10 20 30 40 50 

Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```
#include <stdio.h>
#define MAX 5

float queue[MAX];
int front = -1, rear = -1;

void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
        return;
    }
    if (front == -1) front = 0;
    rear++;
    queue[rear] = value;
    printf("Enqueued: %.2f\n", value);
}

int main() {
    // Inserting elements
    enqueue(10.5); 
    enqueue(20.75);
    enqueue(30.0);
    enqueue(40.25);
    enqueue(50.6);
    enqueue(60.0);  

    return 0;
}
```
Output:
Output 1:
10.50 enqueued
20.70 enqueued
Queue elements: 10.50 20.70 
Output 2:
30.20 enqueued
40.10 enqueued
50.60 enqueued
Queue Overflow
Queue elements: 10.50 20.70 30.20 40.10 50.60 
Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```
#include <stdio.h>
#define MAX 5

float queue[MAX];
int front = -1, rear = -1;

void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
        return;
    }
    if (front == -1) front = 0;
    rear++;
    queue[rear] = value;
    printf("%.2f enqueued\n", value);
}

void dequeue() {
    if (front == -1) {
        printf("Queue is empty, nothing to delete\n");
        return;
    }
    printf("%.2f dequeued\n", queue[front]);
    front++;
    if (front > rear) {
        front = rear = -1;  // reset queue if empty
    }
}

void display() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = front; i <= rear; i++) {
        printf("%.2f ", queue[i]);
    }
    printf("\n");
}

int main() {
    enqueue(10.5);
    enqueue(20.7);
    enqueue(30.2);
    display();

    dequeue();
    display();

    dequeue();
    dequeue();
    display();

    dequeue(); // dequeue from empty queue

    return 0;
}
```

Output:

Output 1:
10.50 enqueued
20.70 enqueued
30.20 enqueued
Queue elements: 10.50 20.70 30.20 
10.50 dequeued
Queue elements: 20.70 30.20 
Output 2:
20.70 dequeued
30.20 dequeued
Queue is empty
Queue is empty, nothing to delete
Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
