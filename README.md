№1
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <algorithm>

void generateAndPrintIntArray(int size) {
    int* arr = new int[size];
    for (int i = 0; i < size; ++i) {
        arr[i] = rand() % 20 - 10; // Генерируем числа от -10 до 9
    }

    std::cout << "Исходный массив: ";
    for (int i = 0; i < size; ++i) {
        std::cout << arr[i] << " ";
    }
    std::cout << std::endl;

    std::sort(arr, arr + size);
    std::cout << "Отсортированный массив: ";
    for (int i = 0; i < size; ++i) {
        std::cout << arr[i] << " ";
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
    for (double& num : arr) {
        std::cin >> num;
    }

    int maxIndex = 0;
    for (int i = 1; i < size; ++i) {
        if (std::abs(arr[i]) > std::abs(arr[maxIndex])) {
            maxIndex = i;
        }
    }

    std::cout << "Номер максимального по модулю элемента: " << maxIndex << std::endl;
    return 0;
}