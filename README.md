# C-Calculator-Final-Program
/*
Filename: ITT-310 C Calculator Final program
Author: Oluwatosin Onifade
Date: 40/23/2022
Version: 4.0
Developing a command interface C-Calculator */

#include <stdio.h>  
// #include <conio.h>  
#include <math.h>  
#include <stdlib.h>  
FILE* fp = fopen_s;

void exit();



struct ops1 {
    int n1, n2, res;
}m;


union ops2 {

    int n1, n2, res1;
    float res2;
    float fp;
}n;

struct add_operation {
    int num;
    int f_num;
}o;

// function prototype

int addition()
{
    // declare a local variable  
    int i, sum = 0;
    printf(" How many numbers you want to add: ");
    scanf_s("%d", &o.num);
    printf(" Enter the numbers: \n ");
    for (i = 1; i <= o.num; i++)
    {
        scanf_s(" %d", &o.f_num);
        sum = sum + o.f_num;
    }
    //  fputs("bi",fp);
    fprintf(fp, " Total Sum of the numbers = %d\n", sum);
    printf(" Total Sum of the numbers = %d\n", sum);
    printf("written to output file successfully...\n");
    return 0;
}


int subtract()
{
    printf(" The first number is: ");
    scanf_s("  %d", &m.n1);
    printf(" The second number is: ");
    scanf_s("  %d", &m.n2);
    m.res = m.n1 - m.n2;
    printf(" The subtraction of %d - %d is: %d\n", m.n1, m.n2, m.res);

    fprintf(fp, " The subtraction of %d - %d is: %d\n", m.n1, m.n2, m.res);
    printf("written to output file successfully...\n");
}

// use multiply() function to multiply two numbers  
int multiply()
{
    printf(" The first number is: ");
    scanf_s("  %d", &m.n1);
    printf(" The second number is: ");
    scanf_s("  %d", &m.n2);
    m.res = m.n1 * m.n2;


    fprintf(fp, " The multiplication of %d * %d is: %d\n", m.n1, m.n2, m.res);

    printf(" The multiplication of %d * %d is: %d", m.n1, m.n2, m.res);
    printf("written to output file successfully...\n");
}

// use divide() function to divide two numbers  
int divide()
{
    printf(" The first number is: ");
    scanf_s("  %d", &m.n1);
    printf(" The second number is: ");
    scanf_s("  %d", &m.n2);

    if (m.n2 == 0)
    {
        printf(" \n Divisor cannot be zero. Please enter another value ");
        scanf_s("%d", &m.n2);
    }
    m.res = m.n1 / m.n2;
    printf(" \n The division of %d / %d is: %d\n", m.n1, m.n2, m.res);
    fprintf(fp, " \n The division of %d / %d is: %d\n", m.n1, m.n2, m.res);

    printf("written to output file successfully...\n");
}

// use sq() function to get the square of the given number  
int sq()
{
    printf(" Enter a number to get the Square: ");
    scanf_s("  %d", &n.n1);

    n.res1 = n.n1 * n.n1;
    printf(" \n The Square of %d is: %d\n", n.n1, n.res1);

    fprintf(fp, " \n The Square of %d is: %d\n", n.n1, n.res1);

    printf("written to output file successfully...\n");
}

// use sqrt1() function to get the square root of the given number   
int sqrt1()
{
    printf(" Enter a number to get the Square Root: ");
    scanf_s("  %d", &n.n2);


    n.res2 = sqrt(n.n2);
    printf(" \n The Square Root  is: %f", n.res2);
    fprintf(fp, " \n The Square Root  is: %f", n.res2);

    printf("written to output file successfully...\n");
}



int main()
{
    // declaration a local variable op;  
    int op;
    do
    {
        // displays the multiple operations of the C Calculator  
        printf(" Select an operation to perform the calculation in C Calculator: ");
        printf(" \n 1 Addition  \t \t 2 Subtraction \n 3 Multiplication \t 4 Division \n 5 Square \t \t 6 Square Root \n 7 Exit \n \n Please, Make a choice ");

        scanf_s("%d", &op); // accepts a numeric input to choose the operation  


    // use switch statement to call an operation  
        switch (op)
        {
        case 1:
            addition(); /* It call the addition() function  to add the given numbers */
            break; // break the function  

        case 2:
            subtract(); /* It call the subtract() function  to subtract the given numbers */
            break; // break the function  

        case 3:
            multiply(); /* It call the multiply() function  to multiply the given numbers */
            break; // break the function  

        case 4:
            divide(); // It call the divide() function  to divide the given numbers  
            break; // break the function  

        case 5:
            sq(); // It call the sq() function  to get the square of given numbers  
            break; // break the function  

        case 6:
            sqrt1(); /* It call the sqrt1() function  to get the square root of given numbers */
            break; // break the function  

        case 7:
            exit(0); // It call the exit() function  to exit from the program  
            break; // break the function  

        default:
            printf(" Something is wrong!! ");
            break;
        }
        printf(" \n \n ********************************************** \n ");
    } while (op != 7);

    fclose(fp);
    return 0;
}

void exit()
{
    // to exit from the program
}
