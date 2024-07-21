# Exercises on Functions

Implement the following functions:

#### `doubledInt()`
- parameters: 1 integer
- return: the integer doubled (x2)


```python
# your code here

def doubledInt(x):
    return x * 2

doubledInt(10)
```




    20



#### `fullName()`
- parameters: three strings: last name, first name, and middle name (optional parameter)
- return: the full name in the following format: {first name} {middle initial}. {last name}. If no middle name is passed it instead returns the name in the following format: {first name} {last name}


```python
# your code here

def fullName(lastname,firstname, middlename = ""):
    try:
        return f"{firstname} {middlename[0]}. {lastname}"
    except IndexError:
       return f"{firstname} {lastname}"
        
fullName("Baruc","Cyrus","C")
```




    'Cyrus C. Baruc'



#### `largest()`
- parameters: two floats
- return: the larger value between the two floats


```python
# your code here

def largest(x,y):
    return max(x,y)

largest(19,91)
    
```




    91



#### `isVerticalLine()`
- parameters: two (float,float) tuples which represent two points in a cartesian plane (x,y)
- return: `True` if the points describe a vertical line and `False` otherwise


```python
# your code here

def isVerticalLine(point1, point2):
    x1,y1 = point1
    x2,y2 = point2
    return x1 == x2 and y1 != y2

isVerticalLine((0,4),(0,5))

```




    True



#### `head()`
- parameters: one list, one integer (optional parameter)
- return: if the list is empty it returns an empty list. if the integer is not passed, it returns the first element of the list, otherwise it returns a list of length n containing the first n elements of the list (where n is the value of the passed integer)


```python
# your code here

def head(list, n = 0):
    if len(list) == 0:
        return list
    elif int == 0:
        return list[0]
    else:
        return list[:n]

x = [2,4,6,8,10,12,14,16,18,20]
        
head(x,5)
```




    [2, 4, 6, 8, 10]



#### `dictionary()`
- parameters: two lists
- return: `None` if the list are not of the same length, otherwise it returns a dictionary where the keys are the first list and values are the second list


```python
# your code here
def dictionary(list1, list2):
    if len(list1) != len(list2):
        return None
    else:
        return dict(zip(list1,list2))

x = ["Month","Date","Year"]
y = [7,11,2024]

dictionary(x,y)
    
```




    {'Month': 7, 'Date': 11, 'Year': 2024}



#### `mean()`
- parameters: a list containining numbers
- return: the mean value of the numbers in the list


```python
# your code here
def mean(x):
    return sum(x)/len(x)

x = [5,10,15,20,25,30]
mean(x)
```




    17.5



#### `variance()`
- parameters: a list containing numbers
- return: the variance of the numbers in the list


```python
# your code here
def variance(list):
    mean = sum(list)/len(list)
    sq_dif = [(x-mean) ** 2 for x in list]
    total_sq_dif = sum(sq_dif)
    var = total_sq_dif / len(list)
    return var

nums =[5,10,15,20,21,22,30]

variance(nums)
        
    
```




    59.10204081632653



#### `filterValues()`
- parameters: a list of numbers, min value (optional paramater), max value (optional parameter)
- return: the same list but filtered based on min and max. If an element is less than min, it is filtered out. If an element is greater than max, it is filtered out. If there is no min value passed, filter negative values. If there is no max value passed, filter values greater than 100


```python
# your code here
def filterValues(numbers, min_value=None, max_value=None):
    if min_value is None:
        min_value = 0
    if max_value is None:
        max_value = 100

    filtered_numbers = [num for num in numbers if min_value <= num <= max_value]
    return filtered_numbers
numbers = [10, -5, 120, 50, 200, 75, -10, 30, 0, 99, 101]

print(filterValues(numbers, max_value = 80))


```

    [10, 50, 75, 30, 0]
    


```python

```
