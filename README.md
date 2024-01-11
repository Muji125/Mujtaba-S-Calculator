#include <stdio.h>
#include <math.h>

void calculator();
void menu();
int input();
//a
void add(int num1, int num2);
void sub(int num1, int num2);
void divide(int num1, int num2);
void multiply(int num1, int num2);
//b
float sine(float num1);
float cosine(float num1);
float tangent(float num1);
float arcsine(float num1);
float arccosine(float num1);
float arctangent(float num1);
//c
float exponentiation(float base, float exponent);
float squareRoot(float num);
float cubeRoot(float num);
float nthRoot(float num, int n);
int factorial(int num);
float absoluteValue(float num);
//d
float logarithmBase10(float num);
float naturalLogarithm(float num);
float customBaseLogarithm(float base, float num);
//e
float mean(int n, int num);
float median(int n, int num);
float mean(int num1, int num2);
float median(int num1, int num2);
int gcd(int num1, int num2);
int lcm(int num1, int num2);
float percentage(float num, float percent);

void menu() {
    printf("Welcome to the Mujtaba`s Calculator\n");
    printf("Simple Calculation\n");
    printf("1. Addition\n");
    printf("2. Subtract\n");
    printf("3. Multiplication\n");
    printf("4. Division\n");
    printf("Complex Calculation\n"); 
    printf("s. Sine\n");
    printf("c. Cosine\n");
    printf("t. Tangent\n");
    printf("S. Arcsine\n");
    printf("C. Arccosine\n");
    printf("T. Arctangent\n");
    printf("E. Exponentiation \n");
    printf("F. Square Root\n");
    printf("G. Cube root\n");
    printf("H. Nth Root\n");
    printf("I. Factorial\n");
    printf("J. Absolute Value\n");
    printf("K. Logarithm\n");
    printf("L. Natural Logarithm\n");
    printf("M. Custom base Logarithm\n");
    printf("N. Mean\n");
    printf("O. Median\n");
    printf("P. GCD Of a Numbers \n");
    printf("Q. LCM Of a Numbers \n");
    printf("R. Percentage Of a Numbers \n");
}

void calculator() {
    char choice;
    char ch;
	menu();
	
    printf("\nEnter your Choice:    \n ");
   

    scanf(" %c", &choice);

    int first_number, second_number, n;
    float base, exponent, result;

    switch (choice) {
        case '1':
            first_number = input();
            second_number = input();
            add(first_number, second_number);
            break;
        case '2':
            first_number = input();
            second_number = input();
            sub(first_number, second_number);
            break;
        case '3':
            first_number = input();
            second_number = input();
            multiply(first_number, second_number);
            break;
        case '4':
            first_number = input();
            second_number = input();
            divide(first_number, second_number);
            break;
        case 's':
            first_number = input();
            sine(first_number);
            break;
        case 'c':
            first_number = input();
            cosine(first_number);
            break;
        case 't':
            first_number = input();
            tangent(first_number);
            break;
        case 'S':
            first_number = input();
            arcsine(first_number);
            break;
        case 'C':
            first_number = input();
            arccosine(first_number);
            break;
        case 'T':
            first_number = input();
            arctangent(first_number);
            break;
        case 'E':
            base = input();
            exponent = input();
            result = exponentiation(base, exponent);
            
            break;
        case 'F':
            first_number = input();
            result = squareRoot(first_number);
            
            break;
        case 'G':
            first_number = input();
            result = cubeRoot(first_number);
            
            break;
        case 'H':
            first_number = input();
            n = input();
            result = nthRoot(first_number, n);
            
            break;
        case 'I':
            first_number = input();
            result = factorial(first_number);
            
            break;
        case 'J':
            first_number = input();
            result = absoluteValue(first_number);
            
            break;
        case 'K':
            first_number = input();
            result = logarithmBase10(first_number);
            
            break;
        case 'L':
            first_number = input();
            result = naturalLogarithm(first_number);
            
            break;
        case 'M':
            base = input();
            first_number = input();
            result = customBaseLogarithm(base, first_number);
            
            break;
        case 'N':
		    first_number = input();
            second_number = input();
            result = mean(first_number, second_number);
            break;
        case 'O':
            first_number = input();
            second_number = input();
            result = median(first_number, second_number);
            break;
        case 'P':
            first_number = input();
            second_number = input();
            result = gcd(first_number, second_number);
            break;
        case 'Q':
            first_number = input();
            second_number = input();
            result = lcm(first_number, second_number);
            break;
        case 'R':
            first_number = input();
            second_number = input();
            result = percentage(first_number, second_number);
            break;
        default:
        	printf("INVALID CHOICE ");
        	break;
       }
  
}

int input(){
    int number;
    printf("Enter a number: ");
    scanf("%d", &number);
    return number;
}

void add(int num1, int num2) {
    printf("The sum of %d and %d is %d\n", num1, num2, num1 + num2);
}

void sub(int num1, int num2) {
    printf("The difference of %d and %d is %d\n", num1, num2, num1 - num2);
}

void multiply(int num1, int num2) {
    printf("The product of %d and %d is %d\n", num1, num2, num1 * num2);
}

void divide(int num1, int num2) {
    if (num2 != 0) {
        printf("The division of %d and %d is %f\n", num1, num2, (float)num1 / num2);
    } else {
        printf("Cannot divide by zero.\n");
    }
}

float sine(float num1) {
    printf("Sin(%f) = %f\n", num1, sin(num1));
    return 0;
}

float cosine(float num1) {
    printf("Cos(%f) = %f\n", num1, cos(num1));
    return 0;
}

float tangent(float num1) {
    printf("Tangent(%f) = %f\n", num1, tan(num1));
    return 0;
}

float arcsine(float num1) {
    double result = asin(num1);
    double result_degrees = result * (180.0 / M_PI);
    printf("Arcsine(%f) = %f degrees\n", num1, result_degrees);
    return result_degrees;
}

float arccosine(float num1) {
    double result = acos(num1);
    double result_degrees = result * (180.0 / M_PI);
    printf("Arccosine(%f) = %f degrees\n", num1, result_degrees);
    return result_degrees;
}

float arctangent(float num1) {
    double result = atan(num1);
    double result_degrees = result * (180.0 / M_PI);
    printf("Arctangent(%f) = %f degrees\n", num1, result_degrees);
    return result_degrees;
}

float exponentiation(float base, float exponent) {
    printf("Exponentiation(%f, %f) = %f\n", base, exponent, pow(base, exponent));
    return pow(base, exponent);
}

float squareRoot(float num) {
    printf("Square Root(%d) = %f\n", num, sqrt(num));
    return sqrt(num);
}

float cubeRoot(float num) {
    printf("Cube Root(%d) = %f\n", num, cbrt(num));
    return cbrt(num);
}

float nthRoot(float num, int n) {
    printf("Nth Root(%d, %d) = %f\n", num, n, pow(num, 1.0 / n));
    return pow(num, 1.0 / n);
}

int factorial(int num) {
	int result=1;
    for (int i = 1; i <= num; i++) {
    result = result * i;
    }

    printf("Factorial of given number is: %d\n", result);

    return 0;
}


float absoluteValue(float num) {
    printf("Absolute Value(%f) = %f\n", num, fabs(num));
    return fabs(num);
}

float logarithmBase10(float num) {
    printf("Logarithm (base 10) of %f = %f\n", num, log10(num));
    return log10(num);
}

float naturalLogarithm(float num) {
    printf("Natural Logarithm (base e) of %f = %f\n", num, log(num));
    return log(num);
}

float customBaseLogarithm(float base, float num) {
    printf("Custom Base Logarithm (%f, %f) = %f\n", base, num, log(num) / log(base));
    return log(num) / log(base);
}
float mean(int num1, int num2) {
    float mean_value = (num1 + num2) / 2.0;
    printf("Mean of %d and %d is %f\n", num1, num2, mean_value);
    return mean_value;
}

float median(int num1, int num2) {
    float median_value = (num1 + num2) / 2.0;
    printf("Median of %d and %d is %f\n", num1, num2, median_value);
    return median_value;
}

int gcd(int num1, int num2) {
    int temp;
    while (num2 != 0) {
        temp = num2;
        num2 = num1 % num2;
        num1 = temp;
    }
    printf("GCD of %d and %d is %d\n", num1, num2, num1);
    return num1;
}

int lcm(int num1, int num2) {
    int gcd_value = gcd(num1, num2);
    int lcm_value = (num1 * num2) / gcd_value;
    printf("LCM of %d and %d is %d\n", num1, num2, lcm_value);
    return lcm_value;
}

float percentage(float num, float percent) {
    float result = (percent / 100.0) * num;
    printf("%.2f%% of %f is %f\n", percent, num, result);
    return result;
}

int main() {
    char continueChoice;
    do {
        calculator();
        printf("Do you want to continue (Y/N)? ");
        scanf(" %c", &continueChoice);
    } while (continueChoice == 'Y' || continueChoice == 'y');

    printf("Goodbye!\n");
    return 0;

}
