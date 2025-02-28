№1
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <algorithm>

void generateAndPrintIntArray(int size) {
    int* arr = new int[size];
    
    // Генерация массива
    for (int* ptr = arr; ptr < arr + size; ++ptr) {
        *ptr = rand() % 20 - 10; // Генерируем числа от -10 до 9
    }

    // Вывод исходного массива
    std::cout << "Исходный массив: ";
    for (int* ptr = arr; ptr < arr + size; ++ptr) {
        std::cout << *ptr << " ";
    }
    std::cout << std::endl;

    // Сортировка массива
    std::sort(arr, arr + size);

    // Вывод отсортированного массива
    std::cout << "Отсортированный массив: ";
    for (int* ptr = arr; ptr < arr + size; ++ptr) {
        std::cout << *ptr << " ";
    }
    std::cout << std::endl;

    // Подсчет различных элементов
    int distinctCount = std::unique(arr, arr + size) - arr;
    std::cout << "Количество различных элементов: " << distinctCount << std::endl;

    delete[] arr; // Освобождение памяти
}

int main() {
    srand(static_cast<unsigned int>(time(0))); // Инициализация генератора случайных чисел
    generateAndPrintIntArray(10); // Генерация массива из 10 элементов
    return 0;
}


№2
#include <iostream>
#include <cmath>

int main() {
    const int size = 10;
    double arr[size];

    // Ввод вещественных чисел
    std::cout << "Введите 10 вещественных чисел: ";
    for (double* ptr = arr; ptr < arr + size; ++ptr) {
        std::cin >> *ptr;
    }

    double* maxPtr = arr; // Указатель на максимальный элемент по модулю

    // Поиск максимального по модулю элемента
    for (double* ptr = arr + 1; ptr < arr + size; ++ptr) {
        if (std::abs(*ptr) > std::abs(*maxPtr)) {
            maxPtr = ptr;
        }
    }

    // Вывод номера максимального по модулю элемента
    std::cout << "Номер максимального по модулю элемента: " << (maxPtr - arr) << std::endl;
    
    return 0;
}