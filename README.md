![image](https://github.com/MatSs1/program_ingener/assets/106054898/7662ec08-19ce-45d8-be86-8d4e4c326dfe)# Тема 8. ВВедение в ООП.
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

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
## Задание №1
### Создайте класс “Car” с атрибутами производитель и модель. Создайте
объект этого класса. Напишите комментарии для кода, объясняющие
его работу. Результатом выполнения задания будет листинг кода с
комментариями.
#### Выполнение:
```python
# Определение класса Car
class Car:
    def __init__(self, make, model):
        # Инициализация атрибутов make и model объекта
        self.make = make
        self.model = model

# Создание объекта myCar класса Car с указанными значениями "Toyota" и "Mazda"
myCar = Car("Toyota", "Mazda")

```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/5ab78b9d-dd35-4337-994b-5d8a15e1554c)

## Задание №2
### Дополните код из первого задания, добавив в него атрибуты и методы
класса, заставьте машину “поехать”. Напишите комментарии для кода,
объясняющие его работу. Результатом выполнения задания будет
листинг кода с комментариями и получившийся вывод в консоль
#### Выполнение:
```python
# Определение класса Car
class Car:
    def __init__(self, make, model):
        # Инициализация атрибутов make и model объекта
        self.make = make
        self.model = model

    def drive(self):
        # Вывод сообщения о том, что происходит езда на автомобиле указанной марки и модели
        print(f"Driving the {self.make} {self.model}")


# Создание объекта myCar класса Car с указанными значениями "Toyota" и "Mazda"
myCar = Car("Toyota", "Mazda")

# Вызов метода drive() для объекта myCar, выводящего сообщение о том, что происходит езда на автомобиле
myCar.drive()

```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/039f57ef-ccf5-45cb-a17d-580a5b832ee4)

## Задание №3
### Создайте новый класс “ElectricCar” с методом “charge” и атрибутом
емкость батареи. Реализуйте его наследование от класса, созданного в
первом задании. Заставьте машину поехать, а потом заряжаться. Напишите комментарии для кода, объясняющие его работу.
Результатом выполнения задания будет листинг кода с комментариями
и получившийся вывод в консоль.

#### Выполнение
```python
# Определение класса Car
class Car:
    def __init__(self, make, model):
        # Инициализация атрибутов make и model объекта
        self.make = make
        self.model = model

    def drive(self):
        # Вывод сообщения о том, что происходит езда на автомобиле
        print(f"Driving the {self.make} {self.model}")

# Определение класса ElectricCar, который является подклассом класса Car
class ElectricCar(Car):
    def __init__(self, make, model, battery_capacity):
        # Вызов конструктора родительского класса с помощью super()
        super().__init__(make, model)
        # Инициализация атрибута battery_capacity объекта
        self.battery_capacity = battery_capacity

    def charge(self):
        # Вывод сообщения о том, что происходит зарядка электрического автомобиля
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")

# Создание объекта my_electric_car класса ElectricCar с указанными значениями
my_electric_car = ElectricCar("Tesla", "Model S", 75)

# Вызов метода drive() для объекта my_electric_car, выводящего сообщение о том, что происходит езда на автомобиле
my_electric_car.drive()

# Вызов метода charge() для объекта my_electric_car, выводящего сообщение о том, что происходит зарядка автомобиля
my_electric_car.charge()

```
#### Результат:
  ![image](https://github.com/MatSs1/program_ingener/assets/106054898/0c67117f-d65d-4eeb-8a05-9ddf9c30a9ee)

## Задание №4
### Реализуйте инкапсуляцию для класса, созданного в первом задании.
Создайте защищенный атрибут производителя и приватный атрибут
модели. Вызовите защищенный атрибут и заставьте машину поехать.
Напишите комментарии для кода, объясняющие его работу.
Результатом выполнения задания будет листинг кода с комментариями
и получившийся вывод в консоль.
#### Выполнение:
```python
# Определение класса Car
class Car:
    def __init__(self, make, model):
        # Инициализация атрибутов make и model объекта
        self.make = make # Защищенный атрибут
        self.model = model # Приватный атрибут

    def drive(self):
        # Вывод сообщения о том, что происходит езда на автомобиле
        print(f"Driving the {self.make} {self.model}")

myCar = Car("Toyota", "Corolla")
print(myCar.make) # Доступ к защищенному атрибуту
# print(myCar.__model) Ошибка! приватный атрибут не доступен
myCar.drive()
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/2e0a0737-319c-481d-bd35-87913111b57f)

## Задание №5
### Реализуйте полиморфизм создав основной (общий) класс “Shape”, а
также еще два класса “Rectangle” и “Circle”. Внутри последних двух
классов реализуйте методы для подсчета площади фигуры. После этого
создайте массив с фигурами, поместите туда круг и прямоугольник,
затем при помощи цикла выведите их площади. Напишите
комментарии для кода, объясняющие его работу. Результатом
выполнения задания будет листинг кода с комментариями и
получившийся вывод в консоль
#### Выполнение:
```python
# Определение базового класса Shape, представляющего геометрическую фигуру
class Shape:
    def area(self):
        # Метод area в базовом классе не имеет конкретной реализации и должен быть переопределен в подклассах
        pass

# Определение подкласса Rectangle, который наследует от базового класса Shape
class Rectangle(Shape):
    def __init__(self, width, height):
        # Инициализация атрибутов width и height объекта
        self.width = width
        self.height = height

    def area(self):
        # Реализация метода area для прямоугольника: площадь = ширина * высота
        return self.width * self.height

# Определение подкласса Circle, который также наследует от базового класса Shape
class Circle(Shape):
    def __init__(self, radius):
        # Инициализация атрибута radius объекта
        self.radius = radius

    def area(self):
        # Реализация метода area для круга: площадь = π * r^2
        return 3.14 * self.radius * self.radius


# Создание объекта класса Rectangle с указанными значениями ширины и высоты
myRectangle = Rectangle(20, 30)

# Вызов метода area для объекта myRectangle, выводящего площадь прямоугольника
result1 = myRectangle.area()



myCircle = Circle(20)
result2 = myCircle.area()

print(result1)
print(result2)




```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/374027c5-3129-475c-ad5a-379e4ef6edf7)


## Самостоятельная работа №1
## Задание №1
### Самостоятельно создайте класс и его объект. Они должны
отличаться, от тех, что указаны в теоретическом материале
(методичке) и лабораторных заданиях. Результатом выполнения
задания будет листинг кода и получившийся вывод консоли.
#### Выполнение:
```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/dc9981b7-e2a8-464b-83cf-02307cba8b2b)


#### Вывод: класс, представляющий книгу, и объект этого класса.

## Задание №2
### Самостоятельно создайте атрибуты и методы для ранее созданного
класса. Они должны отличаться, от тех, что указаны в
теоретическом материале (методичке) и лабораторных заданиях.
Результатом выполнения задания будет листинг кода и
получившийся вывод консоли.
#### Выполнение:
```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

    def info(self):
        print(f"Book Title: {self.title}")
        print(f"Author: {self.author}")

my_book = Book("Anna Carenina", "Tolstoi")

my_book.info()
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/391d335a-f694-490e-b387-621d99a3a813)


### Вывод:класс, представляющий книгу, и объект этого класса. В этом примере книга будет иметь атрибуты title (название) и author (автор), а также метод display_info(), который выводит информацию о книге.

## Задание №3
### Самостоятельно реализуйте наследование, продолжая работать с
ранее созданным классом. Оно должно отличаться, от того, что
указано в теоретическом материале (методичке) и лабораторных
заданиях. Результатом выполнения задания будет листинг кода и
получившийся вывод консоли

#### Выполнение:
```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

    def info(self):
        print(f"Book Title: {self.title}")
        print(f"Author: {self.author}")

my_book = Book("Anna Carenina", "Tolstoi")



class EBook(Book):
    def __init__(self, title, author, format):
        super().__init__(title, author)
        self.format = format

    def info(self):
        super().info()
        print(f"Format: {self.format}")

my_ebook = EBook("Anna Carenina", "Tolstoi", "PDF")

my_ebook.info()
```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/e4b01c99-189c-4342-a33f-0f442cd9efaa)

### Вывод: Использовано наследование для создания нового класса EBook, который расширяет функциональность базового класса Book и добавляет новый атрибут format. Метод info в EBook был переопределен для учета нового атрибута и одновременно использования функциональности родительского класса.

## Задание №4
### Самостоятельно реализуйте инкапсуляцию, продолжая работать с
ранее созданным классом. Она должна отличаться, от того, что
указана в теоретическом материале (методичке) и лабораторных
заданиях. Результатом выполнения задания будет листинг кода и
получившийся вывод консоли.

#### Выполнение:
```python
class Book:
    def __init__(self, title, author):
        self._title = title
        self._author = author

    def get_title(self):
        return self._title

    def set_title(self, title):
        self._title = title

    def get_author(self):
        return self._author

    def set_author(self, author):
        self._author = author

    def info(self):
        print(f"Book Title: {self._title}")
        print(f"Author: {self._author}")

class EBook(Book):
    def __init__(self, title, author, format):
        super().__init__(title, author)
        self._format = format

    def get_format(self):
        return self._format

    def set_format(self, format):
        self._format = format

    def info(self):
        super().info()
        print(f"Format: {self.get_format()}")

my_ebook = EBook("Anna Carenina", "Tolstoi", "PDF")

my_ebook.set_title("New Title")

my_ebook.info()

```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/818aa5fe-2db4-43ec-a428-163e33bfc9d8)


#### Вывод: Атрибуты title, author и format закрытыми (приватными) и предоставим методы для получения и установки этих значений. Таким образом, мы скрываем прямой доступ к атрибутам и обеспечиваем контролируемый доступ к данным.

## Задание №5
### Самостоятельно реализуйте полиморфизм. Он должен отличаться,
от того, что указан в теоретическом материале (методичке) и
лабораторных заданиях. Результатом выполнения задания будет
листинг кода и получившийся вывод консоли.

#### Выполнение:
```python
class Book:
    def __init__(self, title, author):
        self._title = title
        self._author = author

    def get_title(self):
        return self._title

    def set_title(self, title):
        self._title = title

    def get_author(self):
        return self._author

    def set_author(self, author):
        self._author = author

    def info(self):
        print(f"Book Title: {self._title}")
        print(f"Author: {self._author}")

    def read(self):
        print("Reading a physical book.")

class EBook(Book):
    def __init__(self, title, author, format):
        super().__init__(title, author)
        self._format = format

    def get_format(self):
        return self._format

    def set_format(self, format):
        self._format = format

    def info(self):
        super().info()
        print(f"Format: {self.get_format()}")

    def read(self):
        print("Reading an ebook.")

my_book = Book("Anna Carenina", "Tolstoi")
my_ebook = EBook("Padenie", "Kamu", "PDF")

my_book.read()
my_ebook.read()

```
#### Результат:
![image](https://github.com/MatSs1/program_ingener/assets/106054898/170e1b86-6aef-4ae0-a3b3-57df02b9fd30)

#### Вывод: Использованн полиморфизм, где метод read представляет общий интерфейс для чтения книг, но каждый подкласс (Book и EBook) предоставляет свою уникальную реализацию этого метода.

## Общий вывод: 
Объектно-ориентированное программирование (ООП) в Python, как и в других языках программирования, предоставляет ряд преимуществ и инструментов для более удобной и эффективной разработки программ. 
