# Learn Clean Code

# Table of contents
1. [Fundamentals](#fundamentals)
   1. [Meaningful Names](#names)
   2. [Functions](#functions)
   3. [Comments](#comments)
   4. [Formatting](#formatting)
2. [Object and Data Structure](#obj&DS)
3. [Error Handling](#errorHandling)
4. [Unit Tests](#unitTests)
5. [Classes and Systems](#classes)
6. [Concurrency](#concurrency)
7. [Grocery Store Exampe](#example)
8. [Smells and Heuristics](#smells)

## Fundamentals <a name="fundamentals"></a>

### Meaningful Names <a name="names"></a>

1. Use intention revealing names

Names should answer all big questions, if it requires a comment then it's not descriptive enough.
Use pronounceable and searchable names. 

```
int d; // number of days

int numberOfDays;
int numOfDays;
```

Avoid disinformation eg. only refer to something as list if it is actually a list
e.g. accountGroup vs accountList

Avoid Redundancy : developers can understand whether data type is list or map hence appending that
doesn't make sense
```
// bad code
List<String> accountsList = new ArrayList<>();
String nameString;
Integer iNumber; // hungerian notiation to prepend type 
String strName;

// good code
List<String> accounts = new ArrayList<>();
```

Avoid inconsistent naming convention eg developer 1 uses camelCase, another uses snake_case

Names for interfaces and implementations might have some exceptions
```
// both naming conventions are ok
interface ShapeFactory{}

class CircleFactory implements ShapeFactory{}

class ShapeFactoryImpl implements ShapeFactory{}
```

Names for Class : Should be noun eg. Customer, Account and avoid verbs
Names for Methods: Should be verbs or verb-phrases eg. accessors(getters), mutators(setters), predicates(isSomething)
If you have two methods with same name but different functionalities eg. add() one to append string and another to add item to list...then change the name
for any one the methods

No fancy names : e.g. smashConnection() which can simply be closeConnection()
One Word Per Concept: e.g. fetch, retrieve, get...pick any one and stay consistent in all classes i.e. getList, getConn, getDB etc

Use Solution Domain Names: because business analyst is not going to read your code but the developers 
solution-domain-names: names influenced by the technical components eg userController, userRepo
problem-domain-names: names derived from business perspective eg. Invoice, Customer

