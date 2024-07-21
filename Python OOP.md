# Exercises on OOP

You are given the simple class called `Name`. Modify the cell below to make the `Name` class more useful

1. Create an `__init__()` method for `Name`. This function must accept 3 parameters. Inside the `__init__()` method create three attributes: the first parameter must be assigned to the attribute `first`, the second parameter must be assigned to the attribute `middle` and the third paramter to the attribute `last`
2. Create a method called `fullName()`. This returns the full name in the following format {first} {middle initial}. {last}
   > Example: Rubelito R. Abella
4. Create a method called `fullNameLastFirst()`. This returns the full name in the following format {last}, {first} {middle}.
   > Example: Abella, Rubelito Reboquio


```python
class Name:
    def __init__(self):
        self.first = "Cyrus"
        self.middle = "Cueva"
        self.last = "Baruc"
        
    def fullName(self):        
        return f"{self.first} {self.middle[0]}. {self.last}"

    def fullNameLastFirst(self):
        return f"{self.last}, {self.first}, {self.middle}"
       
```

When the `Name` function is complete, create a new class with the following instruction:
1. Create a new class called `TitledName`. This class should inherit from `Name`.
2. Override the `__init__()` class. Instead of accepting 4 parameters, this method accepts 4. The fourth parameter must be assigned to the attribute 'title'. 
3. Create a new method called `titledFullName()` This returns the full name in the following format {title} {first} {middle initial}. {last}
   > Example: Mr. Rubelito R. Abella


```python
#Your code here
class TitledName(Name):    
    def __init__(self):
        self.first = "Cyrus"
        self.middle = "Cueva"
        self.last = "Baruc"
        self.title = "Mr."
    
    def titledFullName(self):
        return f"{self.title} {self.first} {self.middle[0]}. {self.last}"

```


```python
cl = TitledName()
cl.fullName()
```




    'Cyrus C. Baruc'




```python
cl.fullNameLastFirst()
```




    'Baruc, Cyrus, Cueva'




```python
cl.titledFullName()
```




    'Mr. Cyrus C. Baruc'




```python

```
