### EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```c
#include <stdio.h>

struct eligible {
    int age;          
    char name[50];    
};

int main() {
    struct eligible e;

    printf("Enter your name: ");
    scanf("%s", e.name);
    printf("Enter your age: ");
    scanf("%d", &e.age);

    if (e.age <= 6) {
        printf("\nVaccine Eligibility: No");
    } else {
        printf("\nVaccine Eligibility: Yes\n");
    }
    printf("Details:\n");
    printf("Age: %d   ", e.age);
    printf("Name: %s", e.name);
    return 0;
}
```

Output:


<img width="418" height="232" alt="image" src="https://github.com/user-attachments/assets/37c863bb-7518-4171-b5d4-614eb75d620f" />

Result:
Thus, the program is verified successfully

