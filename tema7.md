# Тема 7. Работа с файлами (ввод, вывод).
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
| Задание 6 | + | - |
| Задание 7 | + | - |
| Задание 8 | + | - |
| Задание 9 | + | - |
| Задание 10 | + | - |

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
### Найдите в интернете любую статью (объем статьи не менее 200
слов), скопируйте ее содержимое в файл и напишите программу,
которая считает количество слов в текстовом файле и определит
самое часто встречающееся слово. Результатом выполнения задачи
будет: скриншот файла со статьей, листинг кода, и вывод в консоль,
в котором будет указана вся необходимая информация
#### Выполнение:
```python
from collections import Counter
import string

def count_words(filename):
    try:
        with open(filename, 'r', encoding='utf-8') as file:
            text = file.read().lower()
            text = text.translate(str.maketrans('', '', string.punctuation))
            words = text.split()
            word_count = Counter(words)
            most_common_word, occurrences = word_count.most_common(1)[0]

            return len(words), most_common_word, occurrences
    except FileNotFoundError:
        return None

if __name__ == '__main__':
    file_path = 'input.txt'  #

    result = count_words(file_path)

    if result is not None:
        total_words, most_common, occurrences = result
        print(f"Кол-во слов в файле: {total_words}")
        print(f"Самое часто встречающееся слово: '{most_common}' (встречается {occurrences} раз)")


```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/acec9c7e-ab27-4b2e-b595-1bcd4cccac6a)
![image](https://github.com/MatSs1/program_ingener/assets/106054898/36e5d596-1f9b-4a39-b993-c716f03bb32e)


#### Вывод: Программа считывает текст из файла. Считается количество вхождений каждого слова в тексте с использованием Counter. Из результата выбирается самое часто встречающееся слово и количество его вхождений. Знаки препинания удаляются из текста с использованием .translate(str.maketrans('', '', string.punctuation)), удаляет знаки препинания, разбивает текст на слова с использованием .split(), считает количество слов и определяет самое часто встречающееся слово. 

## Задание №2
### У вас появилась потребность в ведении книги расходов, посмотрев
все существующие варианты вы пришли к выводу что вас ничего не
устраивает и нужно все делать самому. Напишите программу для
учета расходов. Программа должна позволять вводить информацию
о расходах, сохранять ее в файл и выводить существующие данные в
консоль. Ввод информации происходит через консоль. Результатом
выполнения задачи будет: скриншот файла с учетом расходов,
листинг кода, и вывод в консоль, с демонстрацией
работоспособности программы
#### Выполнение:
```python
import json
import os

import loading


def read_expense(expenses, category, amount):
    expenses.append({'category': category, 'amount': amount})

def save(expenses, filename='expenses.txt'):
    with open(filename, 'w') as file:
        for expense in expenses:
            file.write(f"{expense['category']} {expense['amount']}\n")

def load(filename='expenses.txt'):
    if os.path.exists(filename):
        with open(filename, 'r') as file:
            lines = file.readlines()
            expenses = [{'category': line.split()[0], 'amount': float(line.split()[1])} for line in lines]
            return expenses
    else:
        return []


if __name__ == '__main__':
    expenses_list = load()

    while True:
        print("\nВыберите действие:")
        print("1. Добавить расход")
        print("2. Вывести список расходов")
        print("3. Сохранить и выйти")

        choice = input("Введите номер действия: ")

        if choice == '1':
            category = input("Введите категорию расхода: ")
            amount = float(input("Введите сумму расхода: "))
            read_expense(expenses_list, category, amount)
        elif choice == '2':
            save(expenses_list)
        elif choice == '3':
            save(expenses_list)
            break
        else:
            print("Некорректный ввод. Пожалуйста, введите 1, 2 или 3.")


```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/c8eab109-02e3-4b27-9a2a-d822b6d87be5)
![image](https://github.com/MatSs1/program_ingener/assets/106054898/db2a900e-7f19-4c72-843a-193d19285bb7)

#### Вывод: При запуске, программа проверяет наличие файла expenses.txt в текущем рабочем каталоге. Программа находится в цикле, в котором она предоставляет пользователю опции для ввода данных о расходах, просмотра существующих данных или завершения работы. Если пользователь выбирает опцию "Добавить расход", программа запрашивает у пользователя категорию расхода и сумму. При выборе опции "Вывести список расходов" программа отображает все ранее введенные расходы, предоставляя информацию о категории и сумме. Для сохранения данных программа использует функцию save, которая записывает данные в текстовый файл. Если файл существует, она загружает данные о расходах. Пользователь может выбрать "Сохранить и выйти", чтобы сохранить текущие данные в файл expenses.txt и завершить программу.

## Задание №3
### Имеется файл input.txt с текстом на латинице. Напишите программу,
которая выводит следующую статистику по тексту: количество букв
латинского алфавита; число слов; число строк.
• Текст в файле:
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated
#### Выполнение:
```python
def analyze_text(file_path):
    try:
        with open(file_path, 'r', encoding='utf-8') as file:
            text = file.read()

            latin_letters_count = sum(1 for char in text if char.isalpha() and char.isascii())
            word_count = len(text.split())
            line_count = text.count('\n') + 1

            return latin_letters_count, word_count, line_count
    except FileNotFoundError:
        return None

if __name__ == '__main__':
    file_path = 'input.txt'

    result = analyze_text(file_path)

    if result is not None:
        latin_letters, words, lines = result
        print(f"Количество букв латинского алфавита: {latin_letters}")
        print(f"Число слов: {words}")
        print(f"Число строк: {lines}")
    else:
        print("Файл не найден.")
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/9281e385-ccdf-40c7-a049-281619f49a67)
![image](https://github.com/MatSs1/program_ingener/assets/106054898/eb725b47-1031-4f94-b4f5-b6fd5a8a13ac)

#### Вывод: Этот код открывает файл input.txt, считывает его содержимое. Считывает содержимое файла в переменную text. Используя генератор списка и метод строки isalpha(), программа считает количество букв латинского алфавита, проверяя каждый символ текста. Для подсчета слов используется метод split(), который разбивает текст на слова по пробелам.
Для подсчета строк используется метод count('\n'), который подсчитывает количество символов новой строки, а затем добавляется 1, чтобы учесть последнюю строку. Если файл был успешно прочитан и анализ выполнен, программа выводит статистику в консоль.

## Задание №4
### Напишите программу, которая получает на вход предложение,
выводит его в терминал, заменяя все запрещенные слова
звездочками * (количество звездочек равно количеству букв в
слове). Запрещенные слова, разделенные символом пробела,
хранятся в текстовом файле input.txt. Все слова в этом файле
записаны в нижнем регистре. Программа должна заменить
запрещенные слова, где бы они ни встречались, даже в середине
другого слова. Замена производится независимо от регистра: если файл input.txt содержит запрещенное слово exam, то слова exam,
Exam, ExaM, EXAM и exAm должны быть заменены на ****.
• Запрещенные слова:
hello email python the exam wor is
• Предложение для проверки:
Hello, world! Python IS the programming language of thE future. My
EMAIL is....
PYTHON is awesome!!!!
• Ожидаемый результат:
*****, ***ld! ****** ** *** programming language of *** future. My
***** **....
****** ** awesome!!!!
#### Выполнение:
```python
def load_prohibited_words(file_path):
    try:
        with open(file_path, 'r', encoding='utf-8') as file:
            prohibited_words = file.read().lower().split()
        return prohibited_words
    except FileNotFoundError:
        return []

def censor_sentence(sentence, prohibited_words):
    for word in prohibited_words:
        sentence = sentence.replace(word, '*' * len(word))
        sentence = sentence.replace(word.capitalize(), '*' * len(word))
        sentence = sentence.replace(word.upper(), '*' * len(word))
    return sentence

if __name__ == '__main__':
    prohibited_words_file = 'input.txt'
    sentence = input("Введите предложение: ")

    prohibited_words = load_prohibited_words(prohibited_words_file)

    if prohibited_words:
        censored_sentence = censor_sentence(sentence, prohibited_words)
        print("\nрезультат:")
        print(censored_sentence)
    else:
        print(f"Файл {prohibited_words_file} не найден.")
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/41bd69d7-2bf4-4a80-9005-ab7bdc4238fa)
![image](https://github.com/MatSs1/program_ingener/assets/106054898/ff89e720-47a5-4ea1-8fce-cebe6914a563)


#### Вывод: 
Работа кода состоит из: Функция load_prohibited_words загружает запрещенные слова из файла и возвращает их в виде списка в нижнем регистре. Функция censor_sentence заменяет все вхождения запрещенных слов в предложении на звездочки (*), учитывая разные регистры. В основной части программы пользователю предлагается ввести предложение. Если файл с запрещенными словами существует, программа заменяет запрещенные слова в предложении и выводит результат в терминал. Если файл не найден, программа сообщает об этом.


## Задание №5
### Самостоятельно придумайте и решите задачу, в которой будут обязательно использоваться кортеж или список. Проведите минимум три теста для проверки работоспособности вашей задачи.
### Задача: Напишите функцию read_last(lines, file), которая будет открывать определенный файл file и выводить на печать построчно последние строки в количестве lines (на всякий случай проверим, что задано положительное целое число). 
#### Выполнение:
```python
def read_last(lines, file):
    try:
        lines = int(lines)
        if lines <= 0:
            print("Пожалуйста, введите положительное целое число для lines.")
            return

        with open(file, 'r', encoding='utf-8') as f:
            all_lines = f.readlines()

            print(f"Последние {lines} строки из файла {file}:\n")
            for line in all_lines[-lines:]:
                print(line.strip())  

    except ValueError:
        print("Некорректное значение для lines. Пожалуйста, введите положительное целое число.")

if __name__ == '__main__':
    file_path = 'input.txt'
    lines_to_read = input("Введите количество последних строк для вывода: ")
    read_last(lines_to_read, file_path)

```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/a3ba142b-a1bb-4300-9dc0-89683e0bcdbd)
![image](https://github.com/MatSs1/program_ingener/assets/106054898/38c3f5c7-0ece-4b11-8255-c29d321142c4)


#### Вывод: Этот код предоставляет функцию read_last, которая проверяет, что lines является положительным целым числом, а затем открывает файл, читает его строки и выводит последние строки в соответствии с указанным количеством.

## Общий вывод: 
Работа с файлами в Python является важной частью программирования и предоставляет возможности для ввода и вывода данных. 
