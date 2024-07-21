## Python Programs
Discover a curated collection of Python scripts curated for future reuse. Whether you're learning, exploring, or reviewing, you'll find a variety of programs organized for easy navigation and reference.
"


**Challenge1**

Create a program that asks the user for two integers (you will have to call`input()` twice). The program prints the sum of the values


```python
# Solution:

num1 = input("Enter any number below:")
num2 = input("Enter another number:")
total = int(num1) + int(num2)
print("Total is:", total)
```

    Enter any number below: 5
    Enter another number: 15
    

    Total is: 20
    

**Challenge2**

Create a program that asks the user for two integers (you will have to call 
`input()` twice)
If the value of their sum is zero, the program prints the string "Zero .
Otherwise it prints the sum in integer form.


```python
# Solution

num1 = input("Enter a number: ")
num2 = input("Enter another number: ")
total = sum([int(num1), int(num2)])

if total == 0:
    print("Zero")
else:
    print("The sum of the two numbers is:", total)
```

    Enter a number:  5
    Enter another number:  15
    

    The sum of the two numbers is: 20
    

**Challenge3**

Create a program that asks the user integers.
If the value of their sum is zero, the program prints the string "Zero".
Otherwise it prints the sum in integer form.


```python
# Solution

def adder():
    total_sum = 0
    
    while True:
        number_input = input("Enter an integer or type done to finish:")
        if number_input == "done":
            break
            
        try:
            nums = int(number_input)
            total_sum += nums
            
        except ValueError:
            print("Please enter a valid integer")
            
    if total_sum == 0:
        print("Zero")
    else:
        print(total_sum)
        
adder()
```

    Enter an integer or type done to finish: 5
    Enter an integer or type done to finish: 15
    Enter an integer or type done to finish: done
    

    20
    

**Challenge4**

Create a program that asks the user for a name, and the program prints 
"Hello, "


```python
# Solution

print("Hello, ", input("Enter your name below: ")+"!.")

```

    Enter your name below:  Cyrus Baruc
    

    Hello,  Cyrus Baruc!.
    

**Challenge5**

Create a program that asks the user for a name. 
If the number of characters in the name of the person is less than 7 
the program prints "Hello, {name} .
Otherwise it prints "Hi, {name}"


```python
# Solution

name = input("Enter your name: ")

if len(name) < 7:
    print("Hello", name)
else:
    print("Hi", name + "!")

```

    Enter your name:  Cyrus Baruc
    

    Hi Cyrus Baruc!
    

**Challenge6**

Create a program that asks the user for n names. After collecting 
names, print the following for every inputted name:
If the number of characters in the name of the person is less than  ,
the program prints "Hello {name ".
Otherwise it prints "Hi {name}"


```python
# Solution

def greeter():
    names = []

    while True:
        name = input("Enter a name (or type 'done' to finish): ")
        if name.lower() == "done":
            break
        names.append(name)
    
    for name in names:
        if len(name) < 7:
            print(f"Hello, {name}!")
        else:
            print(f"Hi, {name}!")

greeter()

```

    Enter a name (or type 'done' to finish):  Natalia
    Enter a name (or type 'done' to finish):  Serene
    Enter a name (or type 'done' to finish):  Cyanna
    Enter a name (or type 'done' to finish):  Louise
    Enter a name (or type 'done' to finish):  Joy
    Enter a name (or type 'done' to finish):  Cyrus
    Enter a name (or type 'done' to finish):  Andiana
    Enter a name (or type 'done' to finish):  Dodong
    Enter a name (or type 'done' to finish):  done
    

    Hi, Natalia!
    Hello, Serene!
    Hello, Cyanna!
    Hello, Louise!
    Hello, Joy!
    Hello, Cyrus!
    Hi, Andiana!
    Hello, Dodong!
    

**Challenge7**

Create a program that asks the user for a float. The program prints the 
conversion of the number to Fahrenheit


```python
# Solution

cel = float(input("Enter a temperature in celcius from 0 to 100:"))
far = cel * (9/5) + 32
print(f"This is equivalent to {far:.2f} degrees farenheit.")

```

    Enter a temperature in celcius from 0 to 100: 35
    

    This is equivalent to 95.00 degrees farenheit.
    

**Challenge8**

Create a program that asks the user for a float. The program prints the conversion of the number to Fahrenheit.
If the value is below the freezing point of water, the program prints " {fahrenheit} degrees Fahrenheit cold".
If the value is above the boiling point of water, the program prints " {fahrenheit} degrees Fahrenheit hot".
Otherwise the program prints "{fahrenheit} degrees Fahrenheit"


```python
# Solution

num = float(input("Enter a number:"))
result = (num * (9/5)) + 32
if result <= 32:
	print(f"{result}", " degrees Fahrenheit cold")
elif result >= 212:
	print(f"{result}", " degrees Fahrenheit hot")
else:
    print(f"{result}"," degrees Fahrenheit")


```

    Enter a number: 50
    

    122.0  degrees Fahrenheit
    

**Challenge9**

Create a program that asks the user for three floats. The program prints 
the arithmetic mean of the number.s


```python
# Solution

num1 = float(input("Enter any number: "))
num2 = float(input("Enter another number: "))
num3 = float(input("Lastly, enter another number: "))
numlist = [num1,num2,num3]
mean = sum(numlist) / len(numlist)

print(f"The mean of the numbers is {mean}.")
```

    Enter any number:  4
    Enter another number:  5
    Lastly, enter another number:  6
    

    The mean of the numbers is 5.0.
    

**Challenge10**

Create a program that asks the user for three floats.
If the mean is positive, print "Negative mean"
If the mean is negative, print "Positive mean"
If the mean is zero, print "Zero mean"


```python
# Solution

_num1 = input("Enter a number: ")
_num2 = input("Enter another number: ")
_num3 = input("Lastly, enter another number: ")
_mean = sum([int(_num1), int(_num2), int(_num3)])/ len([int(_num1), int(_num2), int(_num3)])
_mean = round(_mean,2)
if _mean > 0:
	print(f"{_mean} : Positive mean")
elif _mean < 0:
	print(f"{_mean} : Negative mean")
else: 
	print(f"{_mean} : Zero mean")
```

    Enter a number:  -50
    Enter another number:  59
    Lastly, enter another number:  99
    

    36.0 : Positive mean
    

**Challenge10**
  
Create a program that asks the user for floats. If the mean is positive, print "Negative mean". If the mean is negative, print "Positive mean". If the mean is zero, print "Zero mean".


```python
# Solution

def mean_calculator():
    numbers = []    
    while True:
        user_input = input("Enter a float (or type 'done' to finish): ")
        if user_input.lower() == 'done':
            break
        try:
            number = float(user_input)
            numbers.append(number)
        except ValueError:
            print("Please enter a valid float.")
    
    if len(numbers) > 0:
        mean_value = sum(numbers) / len(numbers)
        
        if mean_value > 0:
            print("Positive mean")
        elif mean_value < 0:
            print("Negative mean")
        else:
            print("Zero mean")
    else:
        print("No numbers were entered.")

mean_calculator()

```

    Enter a float (or type 'done' to finish):  4
    Enter a float (or type 'done' to finish):  5
    Enter a float (or type 'done' to finish):  6
    Enter a float (or type 'done' to finish):  7
    Enter a float (or type 'done' to finish):  8
    Enter a float (or type 'done' to finish):  9
    Enter a float (or type 'done' to finish):  10
    Enter a float (or type 'done' to finish):  11
    Enter a float (or type 'done' to finish):  12
    Enter a float (or type 'done' to finish):  done
    

    Positive mean
    

**Challenge11**

Create a program that asks a user for a string and an integer. The program prints the string repeated n-times (where is the number inputted by the
user).


```python
# Solution

string = input("Enter a string: ")
integer = int(input("Enter an integer: "))

print(string * integer)
```

    Enter a string:  ha
    Enter an integer:  5
    

    hahahahaha
    

**Challenge12**

Create a program that asks a user for a string and an integer. The program prints the string repeated -times (where is the number inputted by the
user). If the number of characters in the repeated string is greater than 20,the prints "Too long, cannot print" instead.


```python
# Solution

input_1 = input("Enter a string: ")
input_2 = input("Enter a number: ")
result = input_1 * int(input_2)
if len(result) > 20:
	print("Too long, cannot print")	
else:
	print(result)
```

    Enter a string:  The quick brown fox jumps over the lazy dog.
    Enter a number:  10
    

    Too long, cannot print
    


```python

```
