# Тема 6. Базовые коллекции: словари, кортежи.
### Отчет по Теме #8 выполнил:
- Смотрин Матвей Станиславович
- ПИЭ-21-2

| Задание | Лаб. раб. | Сам. раб. |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + | + |
| Задание 7 | + | + |
| Задание 8 | + | + |
| Задание 9 | + | + |
| Задание 10 | + | + |

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
## Задание №1
### Составьте текстовый файл и положите его в одну директорию с
программой на Python. Текстовый файл должен состоять минимум из
двух строк.
#### Выполнение:
```python
f = open('input.txt', 'r')
print(f.readline())
f.close()
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/6cdee897-b1e1-461b-8373-1025d4cdfbc4)

## Задание №2
### Напишите программу, которая выведет только первую строку из
вашего файла, при этом используйте конструкцию open()/close()
#### Выполнение:
```python
f = open('input.txt', 'r')
print(f.readline())
f.close()
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/1c57d263-1e50-482e-9335-a49d4b8539a6)

## Задание №3
### Напишите программу, которая выведет все строки из вашего файла в
массиве, при этом используйте конструкцию open()/close().
#### Выполнение
```python
f = open('input.txt', 'r')
print(f.readlines())
f.close()
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/d828d3bd-1cdc-4fe3-ae88-a5e31ec846f3)

## Задание №4
### Напишите программу, которая выведет все строки из вашего файла в
массиве, при этом используйте конструкцию with open().
#### Выполнение:
```python
with open('input.txt') as f:
    print(f.readlines())
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/6b268c77-a9cc-4e96-af6b-cbfd9827ed18)

## Задание №5
### Напишите программу, которая выведет каждую строку из вашего
файла отдельно, при этом используйте конструкцию with open().
#### Выполнение:
```python
with open('input.txt') as f:
    for line in f:
        print(line)
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/071a62ab-2eeb-4100-bec6-0df1d22b54e6)

### Задание №6
### Напишите программу, которая будет добавлять новую строку в ваш
файл, а потом выведет полученный файл в консоль. Вывод можно
осуществлять любым способом. Обязательно проверьте сам файл,
чтобы изменения в нем тоже отображались
### Выполнение:
```python
with open('input.txt', 'a+') as f:
    f.write('\nIm additional line')

with open('input.txt', 'r') as f:
    result =f.readlines()
    print(result)
```
### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/28c1a0ee-13ee-4dd5-9ada-778e55a75221)

### Задание №7
### Напишите программу, которая перепишет всю информацию, которая
была у вас в файле до этого, например напишет любые данные из
произвольно вами составленного списка. Также не забудьте проверить
что измененная вами информация сохранилась в файле.
### Выполнение:
```python
lines =['one','two','three']
with open('input.txt', 'w') as f:
    for line in lines:
        f.write('\nCycle run' + line)
    print('Done')
```
### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/972cabe6-40ad-4db2-aedd-ca0799c52d92)
![image](https://github.com/MatSs1/program_ingener/assets/106054898/04081d48-8df0-4f2a-bdee-8df00daab482)

### Задание №8
### Выберите любую папку на своем компьютере, имеющую вложенные
директории. Выведите на печать в терминал ее содержимое, как и всех
подкаталогов при помощи функции print_docs(directory).
### Выполнение:
```python
import os

def print_docs(directory):
    all_files = os.walk(directory)
    for catalog in all_files:
        print(f'Папка {catalog[0]} содержит:')
    print(f'Директории:  {", ".join([folder for folder in catalog[1]])}')
    print(f'Файлы:  {", ".join([file for file in catalog[2]])}')
    print('-' *40)


print_docs('C:/Users/smotr/PycharmProjects/pythonProject/venv/input.txt')

```
### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/6121f7a0-afed-4008-9a72-4e7b3de5a143)

### Задание №9
### Документ «input.txt» содержит следующий текст:
Приветствие
Спасибо
Извините
Пожалуйста
До свидания
Ты готов?
Как дела?
С днем рождения!
Удача!
Я тебя люблю.
Требуется реализовать функцию, которая выводит слово, имеющее
максимальную длину (или список слов, если таковых несколько).
Проверьте работоспособность программы на своем наборе данных
### Выполнение:
```python
def longest_words(file):
    with open(file, encoding='utf-8') as f:
        words =f.read().split()
        max_length = len(max(words,key=len))
        for word in words:
            if len(word) == max_length:
                sought_words = word

        if len(sought_words)==1:
            return sought_words[0]
        return sought_words

print(longest_words('input.txt'))

```
### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/4b0a245d-5ec0-4e16-8005-29371803696e)

### Задание №10
### Требуется создать csv-файл «rows_300.csv» со следующими
столбцами:
• № - номер по порядку (от 1 до 300);
Секунда – текущая секунда на вашем ПК;
• Микросекунда – текущая миллисекунда на часах.
Для наглядности на каждой итерации цикла искусственно
приостанавливайте скрипт на 0,01 секунды
### Выполнение:
```python
import csv
import datetime
import time


with open('rows_300.csv', 'w', encoding='utf-8', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['№', 'Секунда', 'Микросекунда'])
    for line in range(1,301):
        writer.writerow([line,datetime.datetime.now().second, datetime.datetime.now().microsecond])
        time.sleep(0.01)

```
### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/255dbb32-f97a-4438-b74f-8f29942b89c1)
![image](https://github.com/MatSs1/program_ingener/assets/106054898/a6f6ddeb-fae4-41a6-a239-545f38c56a54)



## Самостоятельная работа №1
## Задание №1
### При создании сайта у вас возникла потребность обрабатывать данные пользователя в странной форме, а потом переводить их в нужные вам форматы. Вы хотите принимать от пользователя последовательность чисел, разделенных пробелом, а после переформатировать эти данные в список и кортеж. Реализуйте вашу задумку. Для получения начальных данных используйте input(). Результатом программы будет выведенный список и кортеж и значальных данных.
#### Выполнение:
```python
user_input = input("Введите последовательность чисел, разделенных пробелом: ")

numbers_as_strings = user_input.split()

numbers_as_integers = [float(num) for num in numbers_as_strings]

numbers_tuple = tuple(numbers_as_integers)

print("Исходные данные в виде списка:", numbers_as_integers)
print("Исходные данные в виде кортежа:", numbers_tuple)
```
#### Результат:
![image](https://github.com/legendarykk/Programmnaya_Inzheneriya/assets/146570109/aa90e75c-c4b2-4e44-ba11-83b44df1a2e6)

#### Вывод: Программа запрашивает пользователя ввести последовательность чисел, разделенных пробелом, затем преобразует эти данные в список и кортеж целых чисел. Результат работы программы выводится на экран в виде списка и кортежа из введенных пользователем данных.

## Задание №2
### Николай знает, что кортежи являются неизменяемыми, но он очень упрямый и всегда хочет доказать, что он прав. Студент решил создать функцию, которая будет удалять первое появление определенного элемента из кортежа по значению и возвращать кортеж без него. Попробуйте повторить шедевр не признающего авторитеты начинающего программиста. Но учтите, что Николай не всегда уверен в наличии элемента в кортеже (в этом случае кортеж вернется функцией в исходном виде).
#### Выполнение:
```python
def remove_element_from_tuple(input_tuple, element_to_remove):
    if element_to_remove in input_tuple:
        updated_list = list(input_tuple)
        updated_list.remove(element_to_remove)
        return tuple(updated_list)
    else:
        return input_tuple

original_tuple = (1, 2, 3, 4, 5)
element_to_remove = 3
result_tuple = remove_element_from_tuple(original_tuple, element_to_remove)

print("Исходный кортеж:", original_tuple)
print(f"Кортеж после удаления элемента {element_to_remove}:", result_tuple)

```
#### Результат:
![image](https://github.com/legendarykk/Programmnaya_Inzheneriya/assets/146570109/52f51f5b-c052-401f-9384-44e47f6ec585)

#### Вывод: Эта функция, созданная Николаем, принимает кортеж и значение элемента для удаления. Если элемент присутствует в кортеже, то функция удаляет его первое появление, преобразует кортеж в список, удаляет элемент и возвращает обновленный кортеж. В случае отсутствия элемента, исходный кортеж возвращается без изменений.

## Задание №3
### Ребята поспорили кто из них одним нажатием на numpad наберет больше повторяющихся цифр, но не понимают, как узнать победителя. Вам им нужно в этом помочь. Дана строка в виде случайной последовательности чисел от 0 до 9 (длина строки минимум 15 символов). Требуется создать словарь, который в качестве ключей будет принимать данные числа (т. е. ключи будут типом int), а в качестве значений – количество этих чисел в имеющейся последовательности. Для построения словаря создайте функцию, принимающую строку из цифр. Функция должна возвратить словарь из 3-х самых часто встречаемых чисел, также эти значения нужно вывести в порядке возрастания ключа.
#### Выполнение:
```python
def count_and_sort_numbers(input_string):
    numbers_count = {}
    for digit in input_string:
        digit = int(digit)
        numbers_count[digit] = numbers_count.get(digit, 0) + 1

    top_three_numbers = sorted(numbers_count.keys(), key=lambda x: numbers_count[x], reverse=True)[:3]
    top_three_numbers.sort()
    return {num: numbers_count[num] for num in top_three_numbers}

input_sequence = "31415926535897932384626433832795"
result_dict = count_and_sort_numbers(input_sequence)

print("Словарь с тремя самыми часто встречающимися числами:")
for num, count in result_dict.items():
    print(f"Число {num}: {count} раз")
```
#### Результат:
![image](https://github.com/legendarykk/Programmnaya_Inzheneriya/assets/146570109/77c39da1-f361-43e4-9703-a971913cdf8b)

#### Вывод: Данная программа считает и сортирует количество повторений каждой цифры в заданной строке чисел, а затем возвращает словарь с тремя самыми часто встречающимися числами, упорядоченными по возрастанию. Полученные результаты выводятся, указывая число и количество его повторений.

## Задание №4
### Ваш хороший друг владеет офисом со входом по электронным картам, ему нужно чтобы вы написали программу, которая показывала в каком порядке сотрудники входили и выходили из офиса. Определение сотрудника происходит по id. Напишите функцию, которая на вход принимает кортеж и случайный элемент (id), его можно придумать самостоятельно. Требуется вернуть новый кортеж, начинающийся с первого появления элемента в нем и заканчивающийся вторым его появлением включительно. Если элемента нет вовсе – вернуть пустой кортеж. Если элемент встречается только один раз, то вернуть кортеж, который начинается с него и идет до конца исходного.
#### Выполнение:
```python
def extract_employee_log(log_tuple, employee_id):
    first_occurrence = log_tuple.index(employee_id) if employee_id in log_tuple else -1
    second_occurrence = log_tuple.index(employee_id, first_occurrence + 1) if first_occurrence != -1 else -1

    if first_occurrence != -1 and second_occurrence != -1:
        return log_tuple[first_occurrence:second_occurrence + 1]
    elif first_occurrence != -1 and second_occurrence == -1:
        return log_tuple[first_occurrence:]
    else:
        return ()

employee_log = (1, 2, 3, 4, 2, 5, 6, 2, 7, 8)
employee_id_to_extract = 2
result_log = extract_employee_log(employee_log, employee_id_to_extract)

print("Исходный кортеж:", employee_log)
print(f"Подкортеж для сотрудника с ID {employee_id_to_extract}:", result_log)

```
#### Результат:
![image](https://github.com/legendarykk/Programmnaya_Inzheneriya/assets/146570109/dbd820f6-602b-48d8-803c-863cf441358b)

#### Вывод: Эта программа принимает кортеж с записями входа и выхода сотрудников в офис по их ID и случайный элемент ID сотрудника. Затем она возвращает подкортеж, начиная с первого появления этого ID и заканчивая вторым его появлением включительно. Если ID отсутствует в кортеже, программа возвращает пустой кортеж, а если встречается только один раз, возвращается кортеж, начиная с этого элемента и идущий до конца исходного кортежа.

## Задание №5
### Самостоятельно придумайте и решите задачу, в которой будут обязательно использоваться кортеж или список. Проведите минимум три теста для проверки работоспособности вашей задачи.
#### Выполнение:
```python
def calculate_average_scores(student_data):
    if not student_data:
        return []
    averages = []
    for student in student_data:
        student_id, scores = student
        average_score = sum(scores.values()) / len(scores)
        averages.append((student_id, average_score))
    return averages

students = [
    (1, {'Math': 80, 'History': 90, 'English': 75}),
    (2, {'Math': 95, 'History': 85, 'English': 92}),
    (3, {'Math': 78, 'History': 88, 'English': 80}),
]

result_1 = calculate_average_scores(students)
result_2 = calculate_average_scores([])
result_3 = calculate_average_scores([(4, {'Math': 70, 'History': 60, 'English': 65})])

print("Результат 1:", result_1)
print("Результат 2:", result_2)
print("Результат 3:", result_3)
```
#### Результат:
![image](https://github.com/legendarykk/Programmnaya_Inzheneriya/assets/146570109/a7957a83-6ae0-4311-87f5-017a0e35e3ba)

#### Вывод: Данная функция, используя список кортежей с данными о студентах и их оценках по разным предметам, вычисляет средний балл для каждого студента и возвращает список кортежей, содержащих идентификаторы студентов и их средние баллы. В случае отсутствия студентов, функция возвращает пустой список, иначе результаты выводятся, предоставляя информацию о средних баллах для каждого студента.

## Общий вывод: 
Кортежи и списки в Python предоставляют удобные структуры данных для хранения и манипулирования коллекциями элементов. Кортежи являются неизменяемыми, что делает их полезными для представления фиксированных данных, в то время как списки предоставляют гибкость изменения и расширения коллекций. Обе структуры широко используются в программировании для эффективного управления данными, включая хранение, сортировку и фильтрацию, что делает их важными инструментами для разработчиков Python.
