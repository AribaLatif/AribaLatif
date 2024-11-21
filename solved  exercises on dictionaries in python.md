```python
#a) Person Information Dictionary
person_info = {
    "name": "Muhammad",
    "age": 30,
    "city": "Lahore",
    "hobbies": ["reading", "coding", "traveling"]
}
print(person_info)
```

    {'name': 'Muhammad', 'age': 30, 'city': 'Lahore', 'hobbies': ['reading', 'coding', 'traveling']}
    


```python
#b) Word Frequency Counter
def count_word_frequency(text):
    words = text.split()
    frequency = {}
    
    for word in words:
        word = word.lower()
        if word in frequency:
            frequency[word] += 1
        else:
            frequency[word] = 1
            
    return frequency

text = "This is a sample text. This text is for practice purposes."
print(count_word_frequency(text))

```

    {'this': 2, 'is': 2, 'a': 1, 'sample': 1, 'text.': 1, 'text': 1, 'for': 1, 'practice': 1, 'purposes.': 1}
    


```python
#c) Simple Inventory System
inventory = {
    "product1": {"name": "Laptop", "quantity": 10, "price": 1000},
    "product2": {"name": "Smartphone", "quantity": 20, "price": 500}
}

def add_product(inventory, product_id, name, quantity, price):
    inventory[product_id] = {"name": name, "quantity": quantity, "price": price}

def update_quantity(inventory, product_id, quantity):
    inventory[product_id]["quantity"] = quantity

def calculate_total_value(inventory):
    total_value = 0
    for product in inventory.values():
        total_value += product["quantity"] * product["price"]
    return total_value

add_product(inventory, "product3", "Tablet", 15, 300)
update_quantity(inventory, "product1", 5)
print(inventory)
print("Total Inventory Value:", calculate_total_value(inventory))
```

    {'product1': {'name': 'Laptop', 'quantity': 5, 'price': 1000}, 'product2': {'name': 'Smartphone', 'quantity': 20, 'price': 500}, 'product3': {'name': 'Tablet', 'quantity': 15, 'price': 300}}
    Total Inventory Value: 19500
    


```python
#d) Customer Order Analysis
import pandas as pd

# Sample dataset
orders = {
    "customer_id": [1, 2, 3, 1, 2, 3],
    "product_category": ["Electronics", "Fashion", "Home Goods", "Electronics", "Fashion", "Home Goods"],
    "order_value": [100, 50, 200, 150, 75, 250]
}

df = pd.DataFrame(orders)

# Find the most popular product category
popular_category = df["product_category"].value_counts().idxmax()
print("Most Popular Product Category:", popular_category)
```

    Most Popular Product Category: Electronics
    


```python
#e) Student Grades Dictionary
student_grades = {
    "Hahmad": {"Math": 90, "Management": 85, "Ict": 95},
    "Ali": {"Math": 80, "Management": 90, "Ict": 80}
}

def calculate_average_grade(grades):
    average = sum(grades.values()) / len(grades)
    return average

for student, grades in student_grades.items():
    average = calculate_average_grade(grades)
    print(f"{student}'s Average Grade: {average}")
```

    Hahmad's Average Grade: 90.0
    Ali's Average Grade: 83.33333333333333
    


```python
#f) Inventory Management
class Inventory:
    def __init__(self):
        self.products = {}

    def add_product(self, product_id, name, quantity, price):
        self.products[product_id] = {"name": name, "quantity": quantity, "price": price}

    def update_quantity(self, product_id, quantity):
        self.products[product_id]["quantity"] = quantity

    def calculate_total_value(self):
        total_value = 0
        for product in self.products.values():
            total_value += product["quantity"] * product["price"]
        return total_value

    def generate_low_stock_report(self):
        low_stock = {product_id: product for product_id, product in self.products.items() if product["quantity"] < 5}
        return low_stock

inventory = Inventory()
inventory.add_product("product1", "Laptop", 10, 1000)
inventory.add_product("product2", "Smartphone", 20, 500)
print(inventory.products)
inventory.update_quantity("product1", 5)
print(inventory.calculate_total_value())
print(inventory.generate_low_stock_report())
```

    {'product1': {'name': 'Laptop', 'quantity': 10, 'price': 1000}, 'product2': {'name': 'Smartphone', 'quantity': 20, 'price': 500}}
    15000
    {}
    


```python
#g  Student Gradebook
students = {
    "Hamza": {"Math": 85, "Accounting": 90, "programming": 78},
    "Ammar": {"Math": 92, "Accounting": 88, "Programming": 84},
    "Amna": {"Math": 76, "Accounting": 85, "Programming": 80},
    "Ali": {"Math": 89, "Accounting": 92, "Programming": 88}
}

# Function to calculate the average grade for a student
def calculate_average(grades):
    return sum(grades.values()) / len(grades)

# Calculate average grades for each student and store in a new dictionary
average_grades = {}
for student, grades in students.items():
    average_grades[student] = calculate_average(grades)

# Find the highest and lowest grades in a specific subject (e.g., Math)
subject = "Math"
math_grades = {student: grades[subject] for student, grades in students.items()}
highest_math_grade = max(math_grades, key=math_grades.get)
lowest_math_grade = min(math_grades, key=math_grades.get)

# Sort students by their average grades (in descending order)
sorted_students = sorted(average_grades.items(), key=lambda x: x[1], reverse=True)

# Output results
print("Average Grades for Each Student:")
for student, avg in average_grades.items():
    print(f"{student}: {avg:.2f}")

print(f"\nHighest grade in {subject}: {highest_math_grade} with grade {math_grades[highest_math_grade]}")
print(f"Lowest grade in {subject}: {lowest_math_grade} with grade {math_grades[lowest_math_grade]}")

print("\nStudents Sorted by Average Grade (Highest to Lowest):")
for student, avg in sorted_students:
    print(f"{student}: {avg:.2f}")
```

    Average Grades for Each Student:
    Hamza: 84.33
    Ammar: 88.00
    Amna: 80.33
    Ali: 89.67
    
    Highest grade in Math: Ammar with grade 92
    Lowest grade in Math: Amna with grade 76
    
    Students Sorted by Average Grade (Highest to Lowest):
    Ali: 89.67
    Ammar: 88.00
    Hamza: 84.33
    Amna: 80.33
    


```python
# Dictionary to store product information (name, price, quantity)
products = {
    "Laptop": {"price": 1000, "quantity": 10},
    "Phone": {"price": 500, "quantity": 20},
    "Headphones": {"price": 100, "quantity": 30},
    "Keyboard": {"price": 50, "quantity": 50}
}

# Shopping cart dictionary to store items added by the user
cart = {}

# Function to add product to the cart
def add_to_cart(product_name, quantity):
    if product_name in products and products[product_name]["quantity"] >= quantity:
        if product_name in cart:
            cart[product_name]["quantity"] += quantity
        else:
            cart[product_name] = {"price": products[product_name]["price"], "quantity": quantity}
        products[product_name]["quantity"] -= quantity
        print(f"Added {quantity} {product_name}(s) to your cart.")
    else:
        print("Sorry, either the product is out of stock or the quantity is invalid.")

# Function to remove product from the cart
def remove_from_cart(product_name, quantity):
    if product_name in cart and cart[product_name]["quantity"] >= quantity:
        cart[product_name]["quantity"] -= quantity
        products[product_name]["quantity"] += quantity
        if cart[product_name]["quantity"] == 0:
            del cart[product_name]
        print(f"Removed {quantity} {product_name}(s) from your cart.")
    else:
        print("Sorry, you don't have enough of that product in your cart.")

# Function to calculate the total cost of items in the cart
def calculate_total():
    total = 0
    for product_name, details in cart.items():
        total += details["price"] * details["quantity"]
    return total

# Function to apply discount and tax
def apply_discount_and_tax(total, discount_percent, tax_percent):
    discount = (discount_percent / 100) * total
    tax = (tax_percent / 100) * total
    final_total = total - discount + tax
    return final_total, discount, tax

# Example usage
add_to_cart("Laptop", 2)
add_to_cart("Phone", 1)

# Calculate the total cost before discount and tax
total_cost = calculate_total()
print(f"\nTotal cost before discount and tax: ${total_cost:.2f}")

# Apply 10% discount and 5% tax
final_price, discount, tax = apply_discount_and_tax(total_cost, 10, 5)
print(f"Discount applied: ${discount:.2f}")
print(f"Tax applied: ${tax:.2f}")
print(f"Final price after discount and tax: ${final_price:.2f}")
```

    Added 2 Laptop(s) to your cart.
    Added 1 Phone(s) to your cart.
    
    Total cost before discount and tax: $2500.00
    Discount applied: $250.00
    Tax applied: $125.00
    Final price after discount and tax: $2375.00
    


```python

```
