# Abstract fabric

```Python3
from __future__ import annotations
from abc import ABC, abstractmethod

class AbstractFactory(ABC):
    @abstractmethod
    def create_product_a(self) -> AbstractProductA:
        pass

    @abstractmethod
    def create_product_b(self) -> AbstractProductB:
        pass

class ConcreteFactory1(AbstractFactory):
    def create_product_a(self) -> AbstractProductA:
        return ConcreteProductA1()

    def create_product_b(self) -> AbstractProductB:
        return ConcreteProductB1()


class ConcreteFactory2(AbstractFactory):
    def create_product_a(self) -> AbstractProductA:
        return ConcreteProductA2()

    def create_product_b(self) -> AbstractProductB:
        return ConcreteProductB2()

class AbstractProductA(ABC):
    @abstractmethod
    def useful_function_a(self) -> str:
        pass

class ConcreteProductA1(AbstractProductA):
    def useful_function_a(self) -> str:
        return "coucou product A"

class ConcreteProductA2(AbstractProductA):
    def useful_function_a(self) -> str:
        return "coucou product A2"

class AbstractProductB(ABC):
    @abstractmethod
    def useful_function_b(self) -> str:
        pass


class ConcreteProductB1(AbstractProductB):
    class useful_function_b(self) -> str:
        return "Cououc product B1"

class ConcreteProductB2(AbstractProductB):
    class useful_function_b(self) -> str:
        return "Cououc product B2"

def client_code(factory: AbstractFactory) -> None:
    """
    The client code works with factories and products only through abstract
    types: AbstractFactory and AbstractProduct. This lets you pass any factory
    or product subclass to the client code without breaking it.
    """
    product_a = factory.create_product_a()
    product_b = factory.create_product_b()

    print(f"{product_b.useful_function_b()}")
    print(f"{product_b.another_useful_function_b(product_a)}", end="")


if __name__ == "__main__":
    """
    The client code can work with any concrete factory class.
    """
    print("Client: Testing client code with the first factory type:")
    client_code(ConcreteFactory1())

    print("\n")

    print("Client: Testing the same client code with the second factory type:")
    client_code(ConcreteFactory2())        

```
