
#Dzmitry Pilipenka
#Homework-4
#31.03.2025
#Grodno-IT-Academy-Python 3.10


# теперь тесты написаны с использованием библиотеки pytest
# нам нужно ее установить: pip install pytest
# и запустить как обычный файл: pytest test_Homework4.py
# Теперь вы будете знакомы со вторым инструментом для тестирования


#Выведите n-ое число Фибоначчи, используя только временные переменные, циклические операторы и условные операторы. n - вводится.



def fibonacci(n):
    if n < 0:
        raise ValueError("n должно быть неотрицательным")
    elif n == 0:
        return 0
    elif n == 1:
        return 1
    
    a, b = 0, 1
    for _ in range(2, n + 1):
        a, b = b, a + b
    return b


#Определите, является ли число палиндромом (читается слева направо и справа налево одинаково). Число положительное целое, произвольной длины. Задача требует работать только с числами (без конвертации числа в строку или что-нибудь еще).


def palindrome(n):
    return False
def palindrome(n):
    original = n
    reversed_num = 0

    while n > 0:
        digit = n % 10  # Получаем последнюю цифру
        reversed_num = reversed_num * 10 + digit  # Добавляем цифру к перевернутому числу
        n //= 10  # Удаляем последнюю цифру

    return original == reversed_num


#Напишите генератор, который возвращает цифры от S до N, но вместо чисел, кратных 3 пишет Fizz, вместо чисел кратный 5 пишет Buzz, а вместо чисел одновременно кратных и 3 и 5 - FizzBuzz.

def fizz_buzz(S, N):
    for num in range(S, N + 1):
        if num % 3 == 0 and num % 5 == 0:
            yield "FizzBuzz"
        elif num % 3 == 0:
            yield "Fizz"
        elif num % 5 == 0:
            yield "Buzz"
        else:
            yield num

# Пример использования
S = int(input("Введите начальное число S: "))
N = int(input("Введите конечное число N: "))

for result in fizz_buzz(S, N):
    print(result)
