#include <iostream>
#include <cmath>

bool isNarcissistic(int number) {
    int sum = 0;
    int temp = number;
    int digits = log10(number) + 1;

    while (temp > 0) {
        int digit = temp % 10;
        sum += pow(digit, digits);
        temp /= 10;
    }

    return sum == number;
}

int main() {
    for (int i = 100; i < 1000; ++i) {
        if (isNarcissistic(i)) {
            std::cout << i << " ";
        }
    }
    std::cout << std::endl;
    return 0;
}