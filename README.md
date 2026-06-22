1 задание
# Подсчитать количество целых чисел среди a, b, c.
a = float(input("a = "))
b = float(input("b = "))
c = float(input("c = "))
count = 0
if a == int(a):
    count += 1
if b == int(b):
    count += 1
if c == int(c):
    count += 1
print("Количество целых чисел:", count)


# Даны координаты двух точек A и B. Вычислить расстояние между точками. Определить, какая точка находится ближе к началу координат.  
x1, y1 = map(float, input("A (x y): ").split())
x2, y2 = map(float, input("B (x y): ").split())
dist = ((x2 - x1) ** 2 + (y2 - y1) ** 2) ** 0.5
distA = (x1 ** 2 + y1 ** 2) ** 0.5
distB = (x2 ** 2 + y2 ** 2) ** 0.5
print(f"Расстояние AB = {dist:.2f}")
if distA < distB:
    print("Точка A ближе к началу координат")
elif distB < distA:
    print("Точка B ближе к началу координат")
else:
    print("Точки на одинаковом расстоянии")


# Вывести таблицу степеней числа два от нулевой до n, где n вводится  пользователем 

n = int(input("n = "))
i = 0
while i <= n:
    print(f"2^{i} = {2 ** i}")
    i += 1


# Вычислить стоимость поездки на автомобиле на дачу (туда и обратно). Исходными данными являются: расстояние до дачи (км); количество бензина, которое потребляет автомобиль на 100 км пробега; цена 1 литра бензина. 

dist = float(input("Расстояние до дачи (км): "))
consum = float(input("Расход на 100 км (литров): "))
price = float(input("Цена 1 литра бензина: "))
cost = (dist / 100) * consum * price * 2
print(f"Стоимость поездки: {cost:.2f} руб.")


# Вычислить расстояние между двумя точками с координатами (х1, у1) и (х2, у2). Координаты точек должны вводиться пользователем. 

x1, y1 = map(float, input("x1 y1: ").split())
x2, y2 = map(float, input("x2 y2: ").split())
d = ((x2 - x1) ** 2 + (y2 - y1) ** 2) ** 0.5
print(f"Расстояние: {d:.2f}")

# Вывести таблицу стоимости (цена 1кг задается во время работы), например, яблок в диапазоне от А грамм до В грамм с шагом С грамм. 

price_kg = float(input("Цена за 1 кг: "))
A = int(input("От (грамм): "))
B = int(input("До (грамм): "))
C = int(input("Шаг (грамм): "))
weight = A
while weight <= B:
    cost = (weight / 1000) * price_kg
    print(f"{weight} г = {cost:.2f} ")
    weight += C


# Идет k-я секунда суток. Определить, сколько целых часов (Н) и целых минут (М) прошло с начала суток 

k = int(input("Секунда: "))
h = k // 3600
m = (k % 3600) // 60
print(f"Часов: {h}, Минут: {m}")


# Площадь заштрихованной фигуры (квадрат с вырезанным кругом R=a/5).
 
import math
a = float(input("Сторона квадрата: "))
cvad = a ** 2
crug = math.pi * (a / 5) ** 2
s = cvad - crug
print(f"Площадь фигуры: {s:.2f}")



# Вывести значения функции   у = х3   при х = 8, 7.5, …, 2. 

x = 8.0
while x >= 2:
    y = x ** 3
    print(f"x = {x}, y = {y}")
    x -= 0.5


# Вычислить стоимости покупки с учетом скидки. Скидка в 1% предоставляется, если сумма покупки больше 100 руб., в 3% - если сумма больше 500 руб., в 5% - если сумма больше 1000 руб. 

summa = float(input("Сумма покупки: "))
if summa > 1000:
    summa *= 0.95
elif summa > 500:
    summa *= 0.97
elif summa > 100:
    summa *= 0.99
print(f"К оплате: {summa:.2f}")


# Даны целые числа А, В. Если числа не равны, то заменить каждое из них одним и тем же числом, равным большему из исходных, а если равны, то заменить числа нулями 

A = int(input("A = "))
B = int(input("B = "))
if A != B:
    max_val = max(A, B)
    A = B = max_val
else:
    A = B = 0
print(f"A = {A}, B = {B}")



# Если целое число М делится нацело на целое число N, то вывести на экран частное от деления, в противном случае сообщение «М на N не делится» 

M = int(input("M = "))
N = int(input("N = "))
if M % N == 0:
    print(f"Частное: {M // N}")
else:
    print("М на N не делится")

# Даны три действительных числа. Возвести в квадрат те из них, значения которых неотрицательны, и в четвёртую степень – отрицательные 

a = float(input("a = "))
b = float(input("b = "))
c = float(input("c = "))
if a >= 0:
    a = a ** 2
else:
    a = a ** 4
if b >= 0:
    b = b ** 2
else:
    b = b ** 4
if c >= 0:
    c = c ** 2
else:
    c = c ** 4
print(f"a = {a}, b = {b}, c = {c}")


# Перевести время из минут и секунд в секунды. Должна осуществляться проверка правильности введенных пользователем данных и в случае, если данные неверные, выводить соответствующее сообщение 

m = int(input("Минуты: "))
s = int(input("Секунды: "))
if s < 0 or s >= 60:
    print("Ошибка: секунды должны быть от 0 до 59")
else:
    t = m * 60 + s
    print(f"Всего секунд: {t}")


# Перераспределите  значения переменных х  и у так, чтобы в х оказалось большее из этих значений, а в у меньшее 

x = float(input("x = "))
y = float(input("y = "))
if x < y:
    x, y = y, x
print(f"x = {x}, y = {y}")


# Сумма первых n членов ряда: 1/2 + 2/3 + 3/4 + ... + n/(n+1).

n = int(input("n = "))
summa = 0
for i in range(1, n + 1):
    summa += i / (i + 1)
print(f"Сумма: {summa:.4f}")



# Проверить, входит ли цифра М в десятичную запись четырёхзначного числа А. Цифра  M и число A вводятся пользователем 

A = input("Число A: ")
M = input("Цифра M: ")
if M in A:
    print("Цифра входит в число")
else:
    print("Цифра не входит в число")



# 	Вывести 	среднее 	арифметическое 	вводимой 	с 	клавиатуры последовательности чисел. Признаком конца ввода является число 9999 

summa = 0
count = 0
while True:
    num = int(input("Число (9999 - конец): "))
    if num == 9999:
        break
    summa += num
    count += 1
if count == 0:
    print("Нет чисел")
else:
    print(f"Среднее: {summa / count:.2f}")



# Вывести все нечётные и кратные 3 из [a; b].

a = int(input("a = "))
b = int(input("b = "))
print("Нечётные и кратные 3:")
for i in range(a, b + 1):
    if i % 2 != 0 and i % 3 == 0:
        print(i, end=" ")
print()


# Услуги телефонной сети оплачиваются по следующему правилу: за разговоры от А минут в месяц — В рублей, а разговоры сверх установленной нормы оплачиваются из расчета С рублей за минуту. Вычислить плату за пользование телефоном для введенного времени разговоров за месяц 

A = float(input("Норма (мин): "))
B = float(input("Плата за норму (руб): "))
C = float(input("Цена за минуту сверх (руб): "))
time = float(input("Время разговора (мин): "))
if time <= A:
    pay = B
else:
    pay = B + (time - A) * C
print(f"Плата: {pay:.2f} руб.")



# Найти все трехзначные числа, которые при делении на 2 дают остаток 1, при делении на 3 - остаток 2, при делении на 4 - остаток 3, а само число делится на 5 

print("Трёхзначные числа:")
for num in range(100, 1000):
    if num % 2 == 1 and num % 3 == 2 and num % 4 == 3 and num % 5 == 0:
        print(num, end=" ")
print()



# Проверить, принадлежит ли число, введенное с клавиатуры, интервалу (к, х), где к, х – вводятся с клавиатуры 

k = float(input("k = "))
x = float(input("x = "))
num = float(input("Число: "))
if k < num < x:
    print("Принадлежит интервалу")
else:
    print("Не принадлежит интервалу")



# Подсчитать, сколько очков набрала команда в отборочном турнире, если известно, что m встреч она выиграла, n встреч она проиграла, к  встреч закончились ничьими, полагая, что за выигрыш команда получает 2 очка, за ничью – 1 очко, за проигрыш – 0 очков 

m = int(input("Побед: "))
n = int(input("Поражений: "))
k = int(input("Ничьих: "))
points = m * 2 + k * 1
print(f"Очков: {points}")



# Одноклеточная амёба каждые 3 часа делится на 2 клетки. Определить, сколько амёб будет через 3, 6, 9, 12, …, 24 часа 

cells = 1
for hours in range(3, 25, 3):
    cells *= 2
    print(f"Через {hours} ч: {cells} амёб")



# Вычислить стоимости покупки с учетом скидки. Скидка в 3% предоставляется, если сумма покупки больше 1000 руб., в 5% - если сумма больше 5000 руб., в 10% - если сумма больше 10000 руб 

summa = float(input("Сумма покупки: "))
if summa > 10000:
    summa *= 0.90
elif summa > 5000:
    summa *= 0.95
elif summa > 1000:
    summa *= 0.97
print(f"К оплате: {summa:.2f}")



# Вычислить выражение m = min (x + y2, y = z2) + 1

x = float(input("x = "))
y = float(input("y = "))
z = float(input("z = "))

a = x + y ** 2
b = y + z ** 2

if a < b:
    m = a + 1
else:
    m = b + 1

print(f"m = {m}")


# Круг с центром в начале координат (0,0). Заштрихована внутренняя область круга. (рисунок 2)

x = float(input("x = "))
y = float(input("y = "))
if x**2 + y**2 <= 1:
    print("Точка попадает в область")
else:
    print("Точка не попадает в область")



# Вычислить выражение m = min (x2 + y2, y2 = z2) + 1

x = float(input("x = "))
y = float(input("y = "))
z = float(input("z = "))

a = x**2 + y**2
b = y**2 + z**2

if a < b:
    m = a - 4
else:
    m = b - 4

print(f"m = {m}")

# Вывести 	минимальное 	число 	из 	вводимой 	с 	клавиатуры последовательности чисел. Признаком конца ввода является число 9999 

min_num = float('inf')
while True:
    num = int(input("Число (9999 - конец): "))
    if num == 9999:
        break
    if num < min_num:
        min_num = num
if min_num == float('inf'):
    print("Нет чисел")
else:
    print(f"Минимальное: {min_num}")



# Вывести 	максимальное 	число 	из 	вводимой 	с 	клавиатуры последовательности чисел. Признаком конца ввода является число 9999 

max_num = -float('inf')
while True:
    num = int(input("Число (9999 - конец): "))
    if num == 9999:
        break
    if num > max_num:
        max_num = num
if max_num == -float('inf'):
    print("Нет чисел")
else:
    print(f"Максимальное: {max_num}")




ЗАДАНИЕ 3


import math
import random


# Даны координаты двух точек A и B. Вычислить расстояние между точками. Определить, какая точка находится ближе к началу координат. 

def distance(x1, y1, x2, y2):
    return math.sqrt((x2 - x1)**2 + (y2 - y1)**2)

x1, y1 = map(float, input("Введите координаты точки A (x y): ").split())
x2, y2 = map(float, input("Введите координаты точки B (x y): ").split())

dist_ab = distance(x1, y1, x2, y2)
print(f"Расстояние между точками: {dist_ab:.2f}")

dist_a = distance(0, 0, x1, y1)
dist_b = distance(0, 0, x2, y2)

if dist_a < dist_b:
    print("Точка A ближе к началу координат")
elif dist_b < dist_a:
    print("Точка B ближе к началу координат")
else:
    print("Точки находятся на одинаковом расстоянии от начала координат")



# Вычисление с рекурсивным факториалом. Вычислить значение функции  ., где n, m вводятся с клавиатуры. Для вычисления факториала числа использовать рекурсивную функцию 

def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)

n = int(input("Введите n: "))
m = int(input("Введите m: "))

if m > n:
    print("Ошибка: m должно быть меньше или равно n")
else:
    # Пример: y = n! / (n-m)!
    y = factorial(n) / factorial(n - m)
    print(f"Результат: {y:.0f}")



# Дано натуральное число n. Найти и вывести все числа в интервале от 1 до (n-1), у которых произведение всех цифр совпадает с суммой цифр данного числа. Если таких чисел нет, то вывести информацию об этом. Для вычисления  произведения цифр числа составить подпрограмму.  

def product_of_digits(num):
    prod = 1
    for digit in str(abs(num)):
        prod *= int(digit)
    return prod

def sum_of_digits(num):
    return sum(int(digit) for digit in str(abs(num)))

n = int(input("Введите натуральное число n: "))
target_sum = sum_of_digits(n)

print(f"Интервал от 1 до {n-1}")
found = False
for i in range(1, n):
    if product_of_digits(i) == target_sum:
        print(i, end=" ")
        found = True

if not found:
    print("Таких чисел нет")
print()



# Дано  натуральное число n. Найти и вывести все числа в интервале от 1 до (n-1), у которых произведение всех цифр совпадает с произведением цифр данного числа. Если таких чисел  нет,  то вывести информацию об этом. Для вычисления произведения цифр числа составить подпрограмму.  

def product_of_digits(num):
    prod = 1
    for digit in str(abs(num)):
        prod *= int(digit)
    return prod

n = int(input("Введите натуральное число n: "))
target_product = product_of_digits(n)

print(f"Интервал от 1 до {n-1}")
found = False
for i in range(1, n):
    if product_of_digits(i) == target_product:
        print(i, end=" ")
        found = True

if not found:
    print("Таких чисел нет")
print()



# Вычислить значение функции  , n, m - целые числа, вводятся с клавиатуры. Для  вычисления  степени  числа  использовать рекурсивную функцию

def power_recursive(base, exponent):
    if exponent == 0:
        return 1
    if exponent < 0:
        return 1 / power_recursive(base, -exponent)
    return base * power_recursive(base, exponent - 1)

n = int(input("Введите n (основание): "))
m = int(input("Введите m (показатель степени): "))

result = power_recursive(n, m)
print(f"{n}^{m} = {result}")



# Вычислить  значение  функции   , где a и x вводятся  с  клавиатуры. Для вычисления (x2+x+c) написать подпрограмму. 


def calc_expression(x, c):
    return x**2 + x + c

a = float(input("Введите a: "))
x = float(input("Введите x: "))

part1 = calc_expression(x, 2)  
part2 = calc_expression(x, 1)   
part3 = calc_expression(x, 0)    

numerator = part1 + a * part2    
denominator = part3              

if denominator != 0:
    y = numerator / denominator
    print(f"Результат: {y:.2f}")
else:
    print("Ошибка: деление на ноль (x² + x = 0)")

#  Дано натуральное число n (вводится с клавиатуры). Вычислить сумму ряда: Для вычисления факториала числа и возведения числа x в степень написать подпрограммы. 


def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)

def power_func(base, exp):
    result = 1
    for _ in range(abs(exp)):
        result *= base
    if exp < 0:
        return 1 / result
    return result

n = int(input("Введите n: "))
x = float(input("Введите x: "))

summa = 0
for i in range(n + 1):
    summa += power_func(x, i) / factorial(i)

print(f"Сумма ряда: {summa:.4f}")



# Дан массив А размерности n. Сформировать два новых массива B и C: в массив B записать  все положительные элементы массива А, в массив С – все отрицательные. Вывести массивы на экран. 

n = int(input("Введите размер массива: "))
A = []

for i in range(n):
    A.append(float(input(f"A[{i}] = ")))

B = [x for x in A if x > 0]
C = [x for x in A if x < 0]

print(f"Массив A: {A}")
print(f"Массив B (положительные): {B}")
print(f"Массив C (отрицательные): {C}")



# Вывести таблицу степеней  числа mn , где  n  изменяется от -10 до 10,  m  целое  число,  вводится с  клавиатуры.  Для вычисления  степени числа использовать рекурсивную функцию 


def power_recursive(base, exponent):
    if exponent == 0:
        return 1
    if exponent < 0:
        return 1 / power_recursive(base, -exponent)
    return base * power_recursive(base, exponent - 1)

m = int(input("Введите m: "))

print("Таблица степеней:")
for n in range(-10, 11):
    result = power_recursive(m, n)
    print(f"{m}^{n} = {result}")



# Вычислить значение  функции у=2!+4!+ …+  n!, где n –  чётное число, вводится с клавиатуры. Для вычисления факториала числа использовать рекурсивную функцию  


def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)

n = int(input("Введите чётное n: "))

if n % 2 != 0:
    print("Ошибка: n должно быть чётным")
else:
    summa = 0
    for i in range(2, n + 1, 2):
        summa += factorial(i)
    print(f"Сумма: {summa}")



# В массиве целых чисел размерности n (n вводится пользователем) заменить все чётные числа, значения которых меньше среднего арифметического элементов массива на максимальный элемент массива.  

n = int(input("Введите размер массива: "))
arr = []

for i in range(n):
    arr.append(int(input(f"arr[{i}] = ")))

avg = sum(arr) / n
max_el = max(arr)

for i in range(n):
    if arr[i] % 2 == 0 and arr[i] < avg:
        arr[i] = max_el

print(f"Измененный массив: {arr}")


# Дан массив А размерности n. Сформировать два новых массива B и C: в массив B записать  все элементы массива А, большие 3, в массив С – все остальные элементы массива А. Вывести массивы на экран. 

n = int(input("Введите размер массива: "))
A = []

for i in range(n):
    A.append(float(input(f"A[{i}] = ")))

B = [x for x in A if x > 3]
C = [x for x in A if x <= 3]

print(f"A: {A}")
print(f"B (>3): {B}")
print(f"C (<=3): {C}")


# Дан массив размерности n. Вычислить среднее арифметическое элементов массива без учета максимального и минимального элементов. 

n = int(input("Введите размер массива: "))
arr = []

for i in range(n):
    arr.append(float(input(f"arr[{i}] = ")))

if n <= 2:
    print("Ошибка: слишком мало элементов (нужно хотя бы 3)")
else:
    arr_copy = arr.copy()
    arr_copy.remove(max(arr_copy))
    arr_copy.remove(min(arr_copy))
    avg = sum(arr_copy) / len(arr_copy)
    print(f"Среднее без учета max и min: {avg:.2f}")



# В массиве целых чисел размерности n заменить все нечётные числа, значения которых больше среднего арифметического элементов массива на минимальный элемент массива.  


n = int(input("Введите размер массива: "))
arr = []

for i in range(n):
    arr.append(int(input(f"arr[{i}] = ")))

avg = sum(arr) / n
min_el = min(arr)

for i in range(n):
    if arr[i] % 2 != 0 and arr[i] > avg:
        arr[i] = min_el

print(f"Измененный массив: {arr}")



# Дан массив размерности n (n вводится с клавиатуры). Вычислить среднее арифметическое элементов массива без учета максимального элемента. Массив должен быть заполнен случайными числами в диапазоне [-100;100]. 

n = int(input("Введите размер массива: "))

arr = [random.randint(-100, 100) for _ in range(n)]
print(f"Исходный массив: {arr}")

arr_copy = arr.copy()
arr_copy.remove(max(arr_copy))
avg = sum(arr_copy) / len(arr_copy)

print(f"Среднее без учета максимального: {avg:.2f}")

# В массиве целых чисел размерности n (n вводится пользователем) минимальный элемент массива заменить на максимальный. Массив должен быть заполнен случайными числами в диапазоне [-30;30]. 

n = int(input("Введите размер массива: "))

arr = [random.randint(-30, 30) for _ in range(n)]
print(f"Исходный массив: {arr}")

min_idx = arr.index(min(arr))
max_val = max(arr)
arr[min_idx] = max_val

print(f"Измененный массив: {arr}")



# Даны три числа А, В и С. Найти сумму двух наибольших из них. Если числа равны, вывести сообщение об этом. Для нахождения наибольшего из двух чисел написать подпрограмму. 

def max_of_two(a, b):
    return a if a > b else b

A = float(input("A = "))
B = float(input("B = "))
C = float(input("C = "))

if A == B == C:
    print("Все числа равны")
else:
    max1 = max_of_two(max_of_two(A, B), C)
    
    if max1 == A:
        max2 = max_of_two(B, C)
    elif max1 == B:
        max2 = max_of_two(A, C)
    else:
        max2 = max_of_two(A, B)
    
    print(f"Сумма двух наибольших: {max1 + max2:.2f}")


# Ввести  по  строкам  с  клавиатуры  двумерный массив  (4×3)  и  вычислить сумму  его  элементов  по  строкам. 

matrix = []

print("Введите матрицу 4×3:")
for i in range(4):
    row = list(map(float, input(f"Строка {i+1}: ").split()))
    matrix.append(row)

print("\nСуммы по строкам:")
for i in range(4):
    row_sum = sum(matrix[i])
    print(f"Строка {i+1}: {row_sum:.2f}")



# Ввести  по  строкам  с  клавиатуры  двумерный массив  (3×4)  и  вычислить сумму  его  элементов  по  столбцам. 

matrix = []

print("Введите матрицу 3×4:")
for i in range(3):
    row = list(map(float, input(f"Строка {i+1}: ").split()))
    matrix.append(row)

print("\nСуммы по столбцам:")
for j in range(4):
    col_sum = 0
    for i in range(3):
        col_sum += matrix[i][j]
    print(f"Столбец {j+1}: {col_sum:.2f}")



# Вычислить значение функции  , где n, m вводятся с клавиатуры. Для  вычисления факториала числа использовать рекурсивную функцию   

def factorial(k):
    if k <= 1:
        return 1
    return k * factorial(k - 1)

n = int(input("Введите n: "))
m = int(input("Введите m: "))

if n > 5:
    print("Ошибка: n должно быть <= 5, иначе (5-n)! не определён")
else:
    numerator = factorial(5 - n)
    denominator = 4 * factorial(m) - 2 * factorial(n)
    
    if denominator == 0:
        print("Ошибка: деление на ноль (4*m! - 2*n! = 0)")
    else:
        y = numerator / denominator
        print(f"Результат: {y:.4f}")



# Дан массив размерности n. Заменить  все отрицательные элементы массива нулями. Массив должен вводиться пользователем. 

n = int(input("Введите размер массива: "))
arr = []

for i in range(n):
    arr.append(float(input(f"arr[{i}] = ")))

for i in range(n):
    if arr[i] < 0:
        arr[i] = 0

print(f"Измененный массив: {arr}")


# Вычислить значение функции у=1+3!+ 5!+…+  n!, где n – нечётное число, вводится с клавиатуры. Для вычисления факториала числа использовать рекурсивную функцию  

def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)

n = int(input("Введите нечётное n: "))

if n % 2 == 0:
    print("Ошибка: n должно быть нечётным")
else:
    summa = 0
    for i in range(1, n + 1, 2):
        summa += factorial(i)
    print(f"Сумма: {summa}")



# Вывести таблицу степеней  числа mn , где  n  изменяется от a до b шагом h.  a, b, h, m -  целые  числа,  вводятся с  клавиатуры.  Для вычисления  степени числа написать подпрограмму. 

def power_func(base, exponent):
    result = 1
    for _ in range(abs(exponent)):
        result *= base
    if exponent < 0:
        return 1 / result
    return result

a, b, h, m = map(int, input("Введите a, b, h, m: ").split())

print("Таблица степеней:")
n = a
while n <= b:
    result = power_func(m, n)
    print(f"{m}^{n} = {result}")
    n += h



# Вычислить значение функции  , n, m - целые числа, вводятся с клавиатуры. Для  вычисления  степени  числа  составить подпрограмму. 


def power_func(base, exponent):
    result = 1
    for _ in range(abs(exponent)):
        result *= base
    if exponent < 0:
        return 1 / result
    return result

n = int(input("Введите n: "))
m = int(input("Введите m: "))

# Пример: y = n^m + m^n
y = power_func(n, m) + power_func(m, n)
print(f"Результат: {y}")



# В массиве целых чисел размерности n заменить все нечётные числа, кратные 3, на минимальный элемент массива, а отрицательные  элементы -  на максимальный элемент массива. Массив должен быть заполнен случайными числами в диапазоне [-100;100]. 

n = int(input("Введите размер массива: "))

arr = [random.randint(-100, 100) for _ in range(n)]
print(f"Исходный массив: {arr}")

min_el = min(arr)
max_el = max(arr)

for i in range(n):
    if arr[i] % 2 != 0 and arr[i] % 3 == 0:
        arr[i] = min_el
    elif arr[i] < 0:
        arr[i] = max_el

print(f"Измененный массив: {arr}")



# Дано натуральное число n. Определить, является ли это число трехзначным. Для подсчета количества цифр в числе написать подпрограмму. 


def count_digits(num):
    return len(str(abs(num)))

n = int(input("Введите натуральное число n: "))

if count_digits(n) == 3:
    print(f"Число {n} является трёхзначным")
else:
    print(f"Число {n} не является трёхзначным")


#  Определить,  находится  ли  введенное  с клавиатуры число в массиве. Массив должен быть заполнен случайными числами из промежутка [50;50]. Организовать вывод массива на экран. 


n = int(input("Введите размер массива: "))

arr = [random.randint(-50, 50) for _ in range(n)]
print(f"Массив: {arr}")

x = int(input("Введите искомое число: "))

if x in arr:
    print(f"Число {x} находится в массиве")
else:
    print(f"Число {x} не найдено в массиве")



# Вычислить значение функции  	,  где   a  и  x   вводятся  с  клавиатуры.  Для вычисления   написать функцию.  


def calc_expression(x, c):
    return x**2 + x + c

a = float(input("a = "))
x = float(input("x = "))

part1 = calc_expression(x, -3)   
part2 = calc_expression(x, 4)  
part3 = calc_expression(x, 0)  

numerator = a * part1 + part2
denominator = part3

if denominator != 0:
    y = numerator / denominator
    print(f"Результат: {y:.4f}")
else:
    print("Ошибка: деление на ноль (x² + x = 0)")


# Даны три числа А, В и С. Найти произведение двух наименьших из них. Если числа равны, вывести сообщение об этом. Для нахождения наименьшего из двух чисел написать подпрограмму 


def min_of_two(a, b):
    return a if a < b else b

A = float(input("A = "))
B = float(input("B = "))
C = float(input("C = "))

if A == B == C:
    print("Все числа равны")
else:
    min1 = min_of_two(min_of_two(A, B), C)
    
    if min1 == A:
        min2 = min_of_two(B, C)
    elif min1 == B:
        min2 = min_of_two(A, C)
    else:
        min2 = min_of_two(A, B)
    
    print(f"Произведение двух наименьших: {min1 * min2:.2f}")



# Вывести на экран массив с указанной пользователем позиции. Если позиция больше элементов массива, то вывести сообщение об ошибке. 


n = int(input("Введите размер массива: "))
arr = []

for i in range(n):
    arr.append(input(f"arr[{i}] = "))

print(f"Массив: {arr}")

pos = int(input("Введите позицию (индекс): "))

if 0 <= pos < n:
    print(f"Элемент на позиции {pos}: {arr[pos]}")
else:
    print("Ошибка: позиция вне массива")



# Ввести  по  строкам  с  клавиатуры  двумерный массив  (4×4)  и  вычислить  сумму  элементов  его главной диагонали 

matrix = []

print("Введите матрицу 4×4:")
for i in range(4):
    row = list(map(float, input(f"Строка {i+1}: ").split()))
    matrix.append(row)

diag_sum = 0
for i in range(4):
    diag_sum += matrix[i][i]

print(f"Сумма элементов главной диагонали: {diag_sum:.2f}")



# Вывести сумму значений отрицательных  элементов массива размерности n (n вводится пользователем),  сумму индексов положительных элементов массива  и исходный массив.  Ввод массива организовать с клавиатуры. 

n = int(input("Введите размер массива: "))
arr = []

for i in range(n):
    arr.append(float(input(f"arr[{i}] = ")))

sum_negative = 0
sum_indices_positive = 0

for i in range(n):
    if arr[i] < 0:
        sum_negative += arr[i]
    elif arr[i] > 0:
        sum_indices_positive += i

print(f"Исходный массив: {arr}")
print(f"Сумма отрицательных элементов: {sum_negative:.2f}")
print(f"Сумма индексов положительных элементов: {sum_indices_positive}")



# Подсчитать количество  простых  чисел из диапазона  [a,  b], вывести эти числа на экран. Для определения является ли очередное число простым, составить подпрограмму. 


def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(math.sqrt(num)) + 1):
        if num % i == 0:
            return False
    return True

a = int(input("Введите a: "))
b = int(input("Введите b: "))

print(f"Простые числа в диапазоне [{a}, {b}]:")
count = 0
for num in range(a, b + 1):
    if is_prime(num):
        print(num, end=" ")
        count += 1

print(f"\nКоличество простых чисел: {count}")


# Вычислить значение функции  где   a  и  x   вводятся  с  клавиатуры.  Для вычисления  написать функцию.  


def calc_expression(x, c):
    return x**2 + x + c

a = float(input("a = "))
x = float(input("x = "))

part1 = calc_expression(x, 0)  
part2 = calc_expression(x, -2) 
part3 = calc_expression(x, 1)  

numerator = a * part1 + part2
denominator = part3

if denominator != 0:
    y = numerator / denominator
    print(f"Результат: {y:.4f}")
else:
    print("Ошибка: деление на ноль (x² + x + 1 = 0)")
