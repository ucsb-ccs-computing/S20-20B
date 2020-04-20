---
layout: lab
num: lab01
ready: true
desc: "Python Classes"
assigned: 2020-04-19 8:00:00.00-7
due: 2020-04-27 23:59:59.59-7
---

In this lab, you'll have the opportunity to practice with:

* Defining classes in Python
* Defining methods in Python classes
* Testing your functions with pytest

The main idea for this lab is to write a program that will organize Animal objects into an Animal shelter. The program should have the ability to add / remove / search for animals.

In addition to defining classes for Animals and an AnimalShelter, you should test your code correctness by unit testing various scenarios for these classes.

# Instructions

You will need to create three files:
* `Animal.py` - file containing a class definition for an Animal Object.
* `AnimalShelter.py` - file containing a class definition for an AnimalShelter Object.
* `testFile.py` - file containing pytest functions testing both `AnimalShelter` and `Animal` objects.

There will be no starter code for this assignment, but rather the class descriptions and required methods are defined in the specification below.

It's recommended that you organize your lab work in its own directory. This way all files for a lab are located in a single folder. Also, this will be easy to import various files into your code using the `import / from` technique shown in lecture.

## `Animal.py` class

The `Animal.py` file will contain the definition of what an Animal is.

We will define the Animal attributes as follows:

* `species` - str that represents the species of the animal. Your program should ensure that this field will be stored in all upper-case characters.
* `weight` - float that represents the weight (in lbs) of an animal.
* `age` - int that represents the age (in years) of an animal.
* `name` - str that represents the name of the animal. Your program should ensure this field will be stored in all upper-case characters.

You should write a constructor that allows the user to construct an animal object by passing in values for all of the fields. Your constructor should set these attributes with the value `None` by default.

* `__init__(self, species, weight, age, name)`

In addition to your constructor, your class definition should also support "setter" methods that can update the state of the Animal objects:

* `setSpecies(self, species)`
* `setWeight(self, weight)`
* `setAge(self, age)`
* `setName(self, name)`

Each Animal object should be able to call a method that returns a string with all the animal attributes. The string should contain all attributes in the following EXACT format:

<code>
a = Animal("dog", 12.2, 2, "Ruffles")
print(a.toString())

Output:
Species: DOG, Name: RUFFLES, Age: 2, Weight: 12.2
</code>

## AnimalShelter.py

The `AnimalShelter.py` file will contain the definition of what a single AnimalShelter object is.

An AnimalShelter object will contain a dictionary structure where the keys of the dictionary will be a str type representing an Animal's species (all upper-case characters).

The dictionary value will be a list of Animal objects that the AnimalShelter contains. Note that the order of the Animals in the list is based on when the Animal object was inserted into the dictionary structure (most recent Animal inserted will be at the end of the list).

Your code should support the following constructor / methods:

* `__init__(self)` - Constructor that initializes the dictionary structure of the AnimalShelter class. Initially, this dictionary should be empty.
* `addAnimal(self, animal)` - Adds an Animal object (`animal`) to the AnimalShelter. The inserted Animal object should be added to the of the list of existing animals that are the same species. You may assume that an animal with the same attributes does not already exist in the AnimalShelter when this method is called.
* `removeAnimal(self, animal)` - Removes an Animal object (`animal`) from the AnimalShelter if it exists. Your code will need to check and see if the parameter animal object has the same species, name, age, and weight as an existing animal in the AnimalShelter if it is to be removed from the AnimalShelter.
* `getAnimalsBySpecies(self, species)` - Returns a string of all animals of a certain species. This string should consist of a collection of strings - one line for each animal. The order of the Animals in this string will be dictated by the order of the Animals in the AnimalShelter's list for the Animal's species. The Animal `toString()` method should be used when constructing this method's return string. If no Animals of the species exist in the AnimalShelter, then this method returns an empty string ("").
* `doesAnimalExist(self, animal)` - Returns True if the parameter `animal` (with matching species, name, age, and weight) exists in the AnimalShelter. Returns False otherwise.

## `testFile.py` pytest

This file should import your `Animal` and `AnimalShelter` classes so you can write unit tests using pytest to test your functionality is correct. Think of various scenarios and edge cases when testing your code. Even though Gradescope will not use this file when running the automated tests, it is important to provide this file with various test cases (testing is important!!).

## Submission

Once you're done with writing your class definition and tests, Submit your `Animal.py`, `AnimalShelter.py`, and `testFile.py` to the `Lab01` assignment on Gradescope. There will be various unit tests Gradescope will run to ensure your code is working correctly based on the specifications given in this lab.

