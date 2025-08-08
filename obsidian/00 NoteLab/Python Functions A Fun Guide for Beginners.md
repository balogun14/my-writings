## What is a Function? 🤔

Imagine you have a magic box! You put something into the box, the box does some magic, and then gives you something back. That's exactly what a function is in Python!

Think of it like this:
- You give Awwal some ingredients (like rice, tomatoes, and chicken)
- Awwal cooks them in his kitchen (that's the function!)
- Awwal gives you delicious Jollof rice back!

## Why Do We Need Functions? 🎯

### 1. We Don't Like Repeating Ourselves!

Imagine if every time you wanted to say "Hello" to someone, you had to explain what "Hello" means. That would be very tiring! 

Instead, we just say "Hello" and everyone understands. Functions work the same way!

**Without Functions (The Boring Way):**
```python
# Awwal wants to greet his friends from Lagos
print("Hello! My name is Awwal")
print("I live in Lagos, Nigeria") 
print("Nice to meet you!")

# Later, Awwal meets another friend
print("Hello! My name is Awwal")
print("I live in Lagos, Nigeria") 
print("Nice to meet you!")

# And another friend...
print("Hello! My name is Awwal")
print("I live in Lagos, Nigeria") 
print("Nice to meet you!")
```

**With Functions (The Smart Way):**
```python
def awwal_greeting():
    print("Hello! My name is Awwal")
    print("I live in Lagos, Nigeria") 
    print("Nice to meet you!")

# Now Awwal can greet anyone easily!
awwal_greeting()  # First friend
awwal_greeting()  # Second friend  
awwal_greeting()  # Third friend
```

### 2. Functions Make Our Code Like LEGO Blocks! 🧱

Just like you can build different things with the same LEGO blocks, functions let us build different programs with the same pieces of code!

## How to Create a Function 🛠️

Creating a function is like teaching your computer a new trick!

### Step 1: Use the Magic Word "def"
```python
def my_function():
    # Your magic happens here!
    pass
```

### Step 2: Give Your Function a Name
```python
def say_hello():
    print("Hello from Lagos!")
```

### Step 3: Add Your Magic Code
```python
def calculate_age():
    awwal_age = 2024 - 1995
    print(f"Awwal is {awwal_age} years old!")
```

## Functions That Take Ingredients (Parameters) 🥘

Sometimes our magic box needs specific ingredients to work properly!

```python
def make_jollof_rice(rice_cups, people):
    """Awwal's famous Jollof rice calculator!"""
    total_rice = rice_cups * people
    print(f"Awwal needs {total_rice} cups of rice to feed {people} people in Lagos!")
    print("Don't forget the tomatoes and spices! 🍅")

# Let's help Awwal cook for his family
make_jollof_rice(2, 4)  # 2 cups per person, 4 people
make_jollof_rice(3, 10) # For a big Lagos party!
```

**Output:**
```
Awwal needs 8 cups of rice to feed 4 people in Lagos!
Don't forget the tomatoes and spices! 🍅
Awwal needs 30 cups of rice to feed 10 people in Lagos!
Don't forget the tomatoes and spices! 🍅
```

## Functions That Give You Something Back (Return Values) 🎁

Some functions are like vending machines - you put money in, and you get a snack out!

```python
def calculate_bus_fare(from_location, to_location):
    """Calculate bus fare in Lagos"""
    if from_location == "Ikeja" and to_location == "Victoria Island":
        return 500  # 500 Naira
    elif from_location == "Surulere" and to_location == "Lekki":
        return 800  # 800 Naira
    else:
        return 300  # Default fare

# Awwal is planning his trip around Lagos
ikeja_to_vi = calculate_bus_fare("Ikeja", "Victoria Island")
print(f"Awwal needs ₦{ikeja_to_vi} to travel from Ikeja to VI")

surulere_to_lekki = calculate_bus_fare("Surulere", "Lekki")
print(f"From Surulere to Lekki costs ₦{surulere_to_lekki}")
```

## Real-Life Examples from Awwal's Daily Life in Lagos 🌆

### Example 1: Awwal's Morning Routine
```python
def awwal_morning_routine(day_of_week):
    """What Awwal does every morning in Lagos"""
    print("🌅 Good morning Lagos!")
    print("Awwal wakes up and brushes his teeth")
    
    if day_of_week == "Monday":
        print("Time to go to work in Victoria Island!")
        print("Better leave early to beat Lagos traffic! 🚗")
    elif day_of_week == "Saturday":
        print("Weekend! Time to visit the market in Balogun!")
        print("Maybe catch up with friends later 😊")
    else:
        print("Another beautiful day in Lagos!")

# Let's see Awwal's Monday
awwal_morning_routine("Monday")
print("---")
# And his Saturday  
awwal_morning_routine("Saturday")
```

### Example 2: Awwal's Food Calculator
```python
def calculate_meal_cost(meal_name, number_of_people):
    """Help Awwal calculate how much to spend on food"""
    prices = {
        "jollof rice": 1500,    # per person in Naira
        "pounded yam": 2000,
        "suya": 500,
        "plantain": 300
    }
    
    if meal_name in prices:
        total_cost = prices[meal_name] * number_of_people
        return total_cost
    else:
        return 1000 * number_of_people  # Default price

# Awwal is hosting friends from Abuja
jollof_cost = calculate_meal_cost("jollof rice", 6)
suya_cost = calculate_meal_cost("suya", 6)

print(f"Jollof rice for 6 people: ₦{jollof_cost}")
print(f"Suya for 6 people: ₦{suya_cost}")
print(f"Total budget needed: ₦{jollof_cost + suya_cost}")
```

### Example 3: Lagos Weather Helper
```python
def lagos_weather_advice(temperature, is_raining):
    """Awwal's weather helper for Lagos"""
    print("🌤️ Lagos Weather Report:")
    
    if temperature > 30:
        print("It's hot today! Awwal should wear light clothes")
        print("Don't forget to drink lots of water! 💧")
    elif temperature < 20:
        print("Cool weather in Lagos - rare but nice!")
        print("Awwal might need a light jacket")
    
    if is_raining:
        print("☔ It's raining! Traffic will be crazy")
        print("Awwal should leave home extra early")
        print("Don't forget umbrella and waterproof bag!")
    else:
        print("No rain today - perfect for walking around Lagos! 🚶‍♂️")

# Check today's weather for Awwal
lagos_weather_advice(32, True)   # Hot and rainy
print("---")
lagos_weather_advice(25, False)  # Perfect day
```

## Fun Practice Exercises 🎮

### Exercise 1: Create Your Own Greeting Function
```python
def my_greeting(name, city):
    """Create a personalized greeting"""
    print(f"Hello! My name is {name}")
    print(f"I'm from {city}, Nigeria")
    print("Nice to meet you! 🤝")

# Try it out!
my_greeting("Awwal", "Lagos")
my_greeting("Kemi", "Abuja")
```

### Exercise 2: Simple Calculator
```python
def simple_calculator(number1, number2, operation):
    """Awwal's simple calculator"""
    if operation == "add":
        result = number1 + number2
        print(f"{number1} + {number2} = {result}")
    elif operation == "multiply":
        result = number1 * number2
        print(f"{number1} × {number2} = {result}")
    else:
        print("Awwal doesn't know this operation yet!")

# Help Awwal with his math
simple_calculator(10, 5, "add")
simple_calculator(7, 3, "multiply")
```

## Why Functions Are Like Having Superpowers! 🦸‍♂️

1. **Save Time**: Write once, use everywhere! (Like having a magic spell)
2. **Less Mistakes**: Fix a problem once, and it's fixed everywhere
3. **Easy to Understand**: Each function does one thing really well
4. **Share with Friends**: Other people can use your functions too!
5. **Build Big Things**: Combine small functions to create amazing programs!
6. **Easier Refactoring**
7. **Reusability**

## Remember These Important Rules 📋

1. **Function names should be clear**: `calculate_age()` is better than `func1()`
2. **Use comments**: Tell people what your function does
3. **Keep it simple**: One function should do one main thing
4. **Test your functions**: Make sure they work before using them

## Awwal's Final Wisdom 🧠

Functions are like having a helpful friend who remembers how to do things perfectly every time. Instead of explaining how to cook Jollof rice every single time, you just ask your friend (function) to "make Jollof rice" and they know exactly what to do!

Start small, practice often, and soon you'll be creating amazing functions just like Awwal creates amazing  rice in Lagos! 🍚✨

---