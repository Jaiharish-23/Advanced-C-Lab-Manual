### EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```c
#include <stdio.h>

struct numbers {
    int a;
    int b;
};

int add(struct numbers n) {
    return n.a + n.b;
}
int main() {
    struct numbers n;
    printf("Enter the value of a: ");
    scanf("%d", &n.a);
    printf("Enter the value of b: ");
    scanf("%d", &n.b);
    int result = add(n);
    printf("The sum of %d and %d is: %d\n", n.a, n.b, result);
    return 0;
}
```




Output:


<img width="687" height="207" alt="image" src="https://github.com/user-attachments/assets/1b91e525-65b8-45d3-8ac4-c56fb3726bbc" />

Result:
Thus, the program is verified successfully
