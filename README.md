# C-Calculator
#Overview
This is my first project, its a calculator made while i was learning programming basics


#Code


#include <stdio.h>
#include <stdlib.h>

float division(float a, float b);
float multiplication(float a, float b);
float subtraction(float a, float b);
float addition(float a, float b);
int exponentiation(int a, int b);
int squareRoot(int a);
int factorial(int a);

int main() {
    int x, y, result;
    char operator;
    float a, b, resultFloat;

    printf("CALCULATOR\n");
    printf("==========\n\n");

    printf("Operation (+, -, /, *, ^, !, r): \n");
    scanf(" %c", &operator); 

    switch (operator) {
        case '+':
            printf("Type a number: \n");
            scanf("%f", &a);
            printf("Type another number: \n");
            scanf("%f", &b); 
            resultFloat = addition(a, b);
            printf("Result: %.2f\n", resultFloat);
            break;
        case '-':
            printf("Type a number: \n");
            scanf("%f", &a);
            printf("Type another number: \n");
            scanf("%f", &b); 
            resultFloat = subtraction(a, b);
            printf("Result: %.2f\n", resultFloat);
            break;
        case '/':
            printf("Type a number: \n");
            scanf("%f", &a);
            printf("Type another number: \n");
            scanf("%f", &b);
            if (b == 0) {
                printf("Ain't no result for a division by 0\n");
            } else {
                resultFloat = division(a, b);
                printf("Result: %.2f\n", resultFloat);
            }
            break;
        case '*':
            printf("Type a number: \n");
            scanf("%f", &a);
            printf("Type another number: \n");
            scanf("%f", &b);
            resultFloat = multiplication(a, b);
            printf("Result: %.2f\n", resultFloat);
            break;
        case '^':
            printf("Type a number: \n");
            scanf("%d", &x);
            printf("Type another number: \n");
            scanf("%d", &y);
            result = exponentiation(x, y);
            printf("Result: %d\n", result);
            break;
        case '!':
            printf("Type a number: \n");
            scanf("%d", &x);
            result = factorial(x);
            printf("Result: %d\n", result);
            break;
        case 'r':
            printf("Type a number: \n");
            scanf("%d", &x);
            if (x < 0) {
                printf("Ain't no square root of a negative number\n");
            } else {
                result = squareRoot(x);
                printf("Result: %d\n", result);
            }
            break;
        default:
            printf("Invalid operation\n");
    }
    return 0;
}

float division(float a, float b) {
    return a / b;
}

float multiplication(float a, float b) {
    return a * b;
}

float subtraction(float a, float b) {
    return a - b;
}

float addition(float a, float b) {
    return a + b;
}

int exponentiation(int a, int b) {
    int result = 1;
    for (int i = 0; i < b; i++) {
        result *= a;
    }
    return result;
}

int squareRoot(int a) {
    double estimate = a / 2.0;
    for (int i = 0; i < 1000; i++) {
        estimate = (estimate + a / estimate) / 2.0;
    }
    return (int)estimate;
}

int factorial(int a) {
    if (a <= 1) return 1;
    return a * factorial(a - 1);
}

