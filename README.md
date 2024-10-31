// Abstract class
abstract class Animal {
  // Abstract method
  void makeSound();

  // Common method with a default implementation
  void describe() {
    print('This is an animal.');
  }
}

// Superclass with encapsulation
class Mammal {
  // Private variable
  String _species;

  // Constructor
  Mammal(this._species);

  // Getter for the private variable
  String get species => _species;

  // Setter for the private variable
  set species(String species) {
    _species = species;
  }
}

// Subclass that inherits from Mammal and implements Animal
class Dog extends Mammal implements Animal {
  // Constructor
  Dog(String species) : super(species);

  @override
  void makeSound() {
    print('Woof! Woof!');
  }

  @override
  void describe() {
    print('This is a dog of species: ${species}');
  }
}

// Another subclass that inherits from Mammal and implements Animal
class Cat extends Mammal implements Animal {
  // Constructor
  Cat(String species) : super(species);

  @override
  void makeSound() {
    print('Meow!');
  }

  @override
  void describe() {
    print('This is a cat of species: ${species}');
  }
}

void main() {
  // Creating instances of Dog and Cat
  Animal dog = Dog('Canis lupus familiaris');
  Animal cat = Cat('Felis catus');

  // Demonstrating polymorphism
  dog.describe();
  dog.makeSound();
  
  cat.describe();
  cat.makeSound();
}
