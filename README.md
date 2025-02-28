№1
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <algorithm>

void generateAndPrintIntArray(int size) {
    int* arr = new int[size];
    for (int* ptr = arr; ptr < arr + size; ++ptr) {
        *ptr = rand() % 20 - 10; // Генерируем числа от -10 до 9
    }

    std::cout << "Исходный массив: ";
    for (int* ptr = arr; ptr < arr + size; ++ptr) {
        std::cout << *ptr << " ";
    }
    std::cout << std::endl;

    std::sort(arr, arr + size);
    std::cout << "Отсортированный массив: ";
    for (int* ptr = arr; ptr < arr + size; ++ptr) {
        std::cout << *ptr << " ";
    }
    std::cout << std::endl;

    int distinctCount = std::unique(arr, arr + size) - arr;
    std::cout << "Количество различных элементов: " << distinctCount << std::endl;

    delete[] arr;
}

int main() {
    srand(static_cast<unsigned int>(time(0)));
    generateAndPrintIntArray(10);
    return 0;
}


№2

#include <iostream>
#include <cmath>

int main() {
    const int size = 10;
    double arr[size];

    std::cout << "Введите 10 вещественных чисел: ";
    for (double* ptr = arr; ptr < arr + size; ++ptr) {
        std::cin >> *ptr;
    }

    double* maxPtr = arr;
    for (double* ptr = arr + 1; ptr < arr + size; ++ptr) {
        if (std::abs(*ptr) > std::abs(*maxPtr)) {
            maxPtr = ptr;
        }
    }

    std::cout << "Номер максимального по модулю элемента: " << (maxPtr - arr) << std::endl;
    return 0;
}