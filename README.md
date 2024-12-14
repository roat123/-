def calculator():
    """Функция калькулятора."""
    a = int(input("Введите первое число: "))
    b = int(input("Введите второе число: "))
    c = input("Выберите знак (+, -, *, /, %): ")

    # Проверяем введённую операцию
    if c == '+':
        print(f"Результат: {a} + {b} = {a + b}")
    elif c == '-':
        print(f"Результат: {a} - {b} = {a - b}")
    elif c == '*':
        print(f"Результат: {a} * {b} = {a * b}")
    elif c == '/':
        if b != 0:
            print(f"Результат: {a} / {b} = {a / b}")
        else:
            print("Деление на ноль невозможно!")
    elif c == '%':
        if b != 0:
            print(f"Результат: {a} % {b} = {a % b}")
        else:
            print("Деление на ноль невозможно!")
    else:
        print("Ошибка: Неверный знак операции!")


def converter_temperature():
    """Функция конвертера температуры."""
    print("Конвертер температуры:")
    print("1. Цельсий в Фаренгейт")
    print("2. Фаренгейт в Цельсий")
    choice = input("Выберите тип конвертации (1 или 2): ")

    if choice == '1':
        celsius = float(input("Введите температуру в градусах Цельсия: "))
        fahrenheit = celsius * 9 / 5 + 32
        print(f"{celsius}°C = {fahrenheit}°F")
    elif choice == '2':
        fahrenheit = float(input("Введите температуру в Фаренгейтах: "))
        celsius = (fahrenheit - 32) * 5 / 9
        print(f"{fahrenheit}°F = {celsius}°C")
    else:
        print("Ошибка: Неверный пункт меню!")


def converter_currency():
    """Функция конвертера валют."""
    print("Конвертер валют:")
    print("1. Гривны в Доллары")
    print("2. Гривны в Евро")
    print("3. Доллары в Гривны")
    print("4. Евро в Гривны")
    choice = input("Выберите тип конвертации (1, 2, 3 или 4): ")

    # Курсы валют
    usd_rate = 38.0  # 1 USD = 38 грн
    euro_rate = 41.0  # 1 EUR = 41 грн

    if choice == '1':
        hryvnias = float(input("Введите сумму в гривнах: "))
        dollars = hryvnias / usd_rate
        print(f"{hryvnias} грн = {dollars:.2f} USD")
    elif choice == '2':
        hryvnias = float(input("Введите сумму в гривнах: "))
        euros = hryvnias / euro_rate
        print(f"{hryvnias} грн = {euros:.2f} EUR")
    elif choice == '3':
        dollars = float(input("Введите сумму в долларах: "))
        hryvnias = dollars * usd_rate
        print(f"{dollars} USD = {hryvnias:.2f} грн")
    elif choice == '4':
        euros = float(input("Введите сумму в евро: "))
        hryvnias = euros * euro_rate
        print(f"{euros} EUR = {hryvnias:.2f} грн")
    else:
        print("Ошибка: Неверный пункт меню!")


def average_of_three():
    """Функция для вычисления среднего арифметического трёх дробных чисел."""
    print("Вычисление среднего арифметического трёх чисел:")
    num1 = float(input("Введите первое число: "))
    num2 = float(input("Введите второе число: "))
    num3 = float(input("Введите третье число: "))

    # Расчёт среднего арифметического
    average = (num1 + num2 + num3) / 3
    print(f"Среднее арифметическое чисел {num1}, {num2}, {num3} равно {average:.2f}")


def rectangle_calculations():
    """Функция для расчёта площади и периметра прямоугольника."""
    print("Расчёт прямоугольника:")
    print("1. Вычислить площадь")
    print("2. Вычислить периметр")
    choice = input("Выберите действие (1 или 2): ")

    if choice in ['1', '2']:
        length = float(input("Введите длину прямоугольника: "))
        width = float(input("Введите ширину прямоугольника: "))

        if choice == '1':
            area = length * width
            print(f"Площадь прямоугольника с длиной {length} и шириной {width} равна {area:.2f}")
        elif choice == '2':
            perimeter = 2 * (length + width)
            print(f"Периметр прямоугольника с длиной {length} и шириной {width} равен {perimeter:.2f}")
    else:
        print("Ошибка: Неверный пункт меню!")


# Главное меню
def main():
    while True:
        print("\nГлавное меню:")
        print("1. Калькулятор")
        print("2. Конвертер температуры")
        print("3. Конвертер валют")
        print("4. Среднее арифметическое трёх чисел")
        print("5. Расчёт площади и периметра прямоугольника")
        print("6. Выход")
        choice = input("Выберите программу (1, 2, 3, 4, 5 или 6): ")

        if choice == '1':
            calculator()
        elif choice == '2':
            converter_temperature()
        elif choice == '3':
            converter_currency()
        elif choice == '4':
            average_of_three()
        elif choice == '5':
            rectangle_calculations()
        elif choice == '6':
            print("Выход из программы...")
            break
        else:
            print("Ошибка: Неверный пункт меню!")


# Запуск программы
if __name__ == "__main__":
    main()
