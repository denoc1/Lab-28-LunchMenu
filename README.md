# Lab 28: LunchMenu

## Objective:
In this lab, you will create a program that models a menu system for a lunch counter. The menu includes a variety of sandwiches, salads, drinks, and combos. Each combo consists of three items: a sandwich, a salad, and a drink. You will implement several classes to represent these menu items and calculate the prices of combos.

Your task is to implement a system where:
- **Sandwiches**, **Salads**, and **Drinks** are individual menu items.
- A **Combo** is a combination of one sandwich, one salad, and one drink.
- The price of a **Combo** is calculated by summing the two highest-priced items and adding 20% of the lowest-priced item.

Additionally, you will add:
- **Dollar signs** to the display of prices.
- **Rounding** to two decimal places for prices.

## Classes to Create:
You will create four classes: `MenuItem`, `Sandwich`, `Salad`, `Drink`, and `Combo`.

### Menu Items and Prices

Here are some examples of menu items that might be declared to test your code.  Please note, I can make up any items so make sure your code works on all possibilities.

#### Sandwiches:
- **Cheeseburger**: $4.00
- **Club Sandwich**: $5.00

#### Salads:
- **Spinach Salad**: $2.50
- **Coleslaw**: $1.75

#### Drinks:
- **Orange Soda**: $1.00
- **Cappuccino**: $2.50

### Explanation:
- The `MenuItem` class is the parent class.
- The `Sandwich`, `Salad`, `Drink` and `Combo` classes are all child classes that extend `MenuItem`.
- Each child class contains menu items with specific prices.
- In the `Combo` class, the name of the combo is formed by combining the names of a sandwich, salad, and drink, and the price is calculated according to the rules specified earlier.

### 1. MenuItem Class:
The `MenuItem` class will serve as the parent class for all the menu items. It should represent a generic menu item and include the following:

- Two private instance variables:
  - `String name` – The name of the menu item.
  - `double price` – The price of the menu item.

- A constructor to initialize the `name` and `price` fields.

- **Methods:**
  - `getName()`: Returns the name of the menu item.
  - `getPrice()`: Returns the price of the menu item.
  - `getFormattedPrice()`: Returns the price as a formatted string with a dollar sign and rounded to two decimal places (e.g., "$4.25").
  - `toString()`: Returns a string that includes the name and formatted price of the menu item.

### 2. Sandwich, Salad, and Drink Classes:
The `Sandwich`, `Salad`, and `Drink` classes should each extend the `MenuItem` class and represent specific types of menu items. Each of these classes should:

- Have a constructor that calls the parent class constructor using the super() constructor.

### 3. Combo Class:

The `Combo` class will represent a combo meal consisting of a sandwich, salad, and drink. This class will also extend the `MenuItem` class.

- **Constructor**:
  - The constructor should accept a `Sandwich`, `Salad`, and `Drink` object as parameters.
  - The name of the combo should be a combination of the three items' names, formatted as: 
    - `"Sandwich Name/Salad Name/Drink Name Combo"`. 
    - For example, if the sandwich is "Cheeseburger", the salad is "Spinach Salad", and the drink is "Orange Soda", the combo name should be `"Cheeseburger/Spinach Salad/Orange Soda Combo"`.
  
  - **Price Calculation**:
    - The price of the combo is calculated as the sum of the two highest-priced items plus 20% of the lowest-priced item.
  
### Example Combo:
For example, a combo consisting of a **Cheeseburger**, **Spinach Salad**, and **Orange Soda** would have the following:
- **Name**: "Cheeseburger/Spinach Salad/Orange Soda Combo"
- **Price Calculation**:
  - Sandwich: $4.00
  - Salad: $2.50
  - Drink: $1.00
  - Combo price = $6.50

  
  - `toString()`: This method should return a string with both the combo name and the price. You should format the price to include a dollar sign and round to two decimal places.
   
    - ### Required Methods for Combo Class

The `Combo` class should have overloaded methods for `getName()`, `toString()`, and `getPrice()` to provide correct and useful output for Combo objects.

- **`getName()`**: Should return the name of the combo, which is the combination of the sandwich, salad, and drink names, followed by "Combo".
   Example: `"Cheeseburger/Spinach Salad/Orange Soda Combo"`.
- **`toString()`**: Should provide a string representation of the combo, including the combo name and its price.
    Example: `"Cheeseburger/Spinach Salad/Orange Soda Combo - $6.50"`. 
- **`getPrice()`**: Should return the price of the combo, calculated based on the sum of the two highest-priced items plus 20% of the lowest-priced item.
    Example:  6.50

### Combo Class Behavior

When initializing a `Combo` object, the order of the menu items matters. The `Combo` class should only allow the combination of a **Sandwich**, **Salad**, and **Drink**. If an incorrect combination is provided, a **compile-time error** should occur.

Examples of valid and invalid `Combo` object initializations:

```java
Combo combo = new Combo(sandwich, salad, drink);  // Compiles without error

Combo combo1 = new Combo(salad, sandwich, drink);  // Compile-time error: wrong order of items
Combo combo2 = new Combo(sandwich, salad, salad);  // Compile-time error: two salads, no drink
```

### Key Points:
- Ensure the combo's name is a combination of the sandwich, salad, and drink names.
- Correctly calculate the price: sum of two highest prices plus 20% of the lowest.
- Implement `getName()`, `toString()`, and `getPrice()` methods for the `Combo` class.

You do not need to include header documentation for this code.  Use in-line documentation if you think it would be helpful.

