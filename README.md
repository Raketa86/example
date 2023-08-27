class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        self._salary = 1000  # Модификатор доступа protected

    def greeting(self):
        print(f"Hello, my name is {self.name}.")

    def get_salary(self):
        return self._salary


class Employee(Person):
    def __init__(self, name, age, salary):
        super().__init__(name, age)
        self.__salary = salary  # Модификатор доступа private

    def get_salary(self):  # Переопределение метода
        return self.__salary


person = Person("John", 30)
person.greeting()
print(person.age)  # Выводит 30
print(person.name)  # Выводит "John"
print(person._salary)  # Выводит 1000

employee = Employee("Bob", 25, 5000)
employee.greeting()
print(employee.age)  # Выводит 25
print(employee.name)  # Выводит "Bob"
print(employee._salary)  # Выводит 1000
print(employee.get_salary())  # Выводит 5000
print(employee.__salary)  # Ошибка, так как __salary является приватным
