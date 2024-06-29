# calci
#include <iostream>
#include <sstream>
#include <cmath>
using namespace std;

int add(int n1, int n2) {
    return n1 + n2;
}

int sub(int n1, int n2) {
    return n1 - n2;
}

int mul(int n1, int n2) {
    return n1 * n2;
}

int divide(int n1, int n2) {
    return n1 / n2;
}

int main() {
    char operation;
    string input1, input2;
    int num1, num2, result;
    cout << "Enter the first number: ";
    cin >> input1;
    cout << "Enter the operation (+, -, *, /): ";
    cin >> operation;
    cout << "Enter the second number: ";
    cin >> input2;

    // Convert input to int
    stringstream ss1(input1), ss2(input2);
    ss1 >> num1;
    ss2 >> num2;   
    switch (operation) {
        case '+':
            result = add(num1, num2);
            break;
        case '-':
            result = sub(num1, num2);
            break;
        case '*':
            result = mul(num1, num2);
            break;
        case '/':
            if (num2 != 0) {
                result = divide(num1, num2);
            } else {
                cout << "Cannot divide by zero" << endl;
                return 1;
            }
            break;
        default:
            cout << "Invalid operation!" << endl;
            return 1;
    }

    
    cout << "Result: " << result << endl;

    return 0;
}

