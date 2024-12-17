№1
import random

def get(p):
    while True:
        try:
            value = int(input(p))
            if value > 0:
                return value
            else:
                print("Введите положительное целое число.")
        except ValueError:
            print("Ошибка ввода. Попробуйте снова.")

M = get("Введите количество строк (M): ")
N = get("Введите количество столбцов (N): ")

matrix = [[random.randint(1, 100) for _ in range(N)] for _ in range(M)]

print("Исходный список:")
for row in matrix:
    print(row)

# Перестановка строк
for i in range(M):
    if i % 2 == 1:
        matrix[i] = matrix[i][::-1]

print("Измененный список:")
for row in matrix:
    print(row)


№2
import random

def get(p):
    while True:
        try:
            value = int(input(p))
            if value > 0:
                return value
            else:
                print("Введите положительное целое число.")
        except ValueError:
            print("Ошибка ввода. Попробуйте снова.")

M = get("Введите количество строк (M): ")
N = get("Введите количество столбцов (N): ")

matrix = [[random.randint(-50, 50) for _ in range(N)] for _ in range(M)]

print("Исходный список:")
for row in matrix:
    print(row)

# Характеристика строки
def characteristic(row):
    return sum(x for x in row if x > 0 and x % 2 == 0)

char_list = [(characteristic(row), row) for row in matrix]
char_list.sort(reverse=True, key=lambda x: x[0])

sorted = [row for _, row in char_list]

print("Характеристики:")
for char, _ in char_list:
    print(char)

print("Измененный список:")
for row in sorted:
    print(row)

№3
def get():
    count = {}
    for _ in range(int(input("Введите количество стран: "))):
        entry = input("Введите страну и города (например, 'Россия: Москва, Санкт-Петербург'): ")
        country, cities = entry.split(':')
        count[country.strip()] = [city.strip() for city in cities.split(',')]
    return count

count = get()
city = input("Введите город для поиска страны: ")

f = next((country for country, cities in count.items() if city in cities), "Не найдено")
print("Страна, где находится город:", f)