## Python Loops

Curated selection of Python scripts focusing on loops, tailored for future reference.

### Challenge1: Horizontal Bar Chart

In the cell below you are given a list of integers. You are to create a horizontal bar chart to rerpresent the data in the list.

For every integer in the list, print a bar. The bar is created by repeating the character `#`. If the integer's value is n, the bar printed must be n `#`s long. 
Include numbering to label each bar. For example, given the data:
```
data = [3,2,4]
```
The chart should look like the following:
```
1. ###
2. ##
3. ####
```


```python
values = [1,3,2,5,0,7]

# Solution

i = 1
for value in values:    
    print(f"{i}.","#" * value)
    i += 1
```

    1. #
    2. ###
    3. ##
    4. #####
    5. 
    6. #######
    

### Challenge2: Full Names

In the cell below you are given three lists. A list of first names, a list of middle names, and a list of last names. 

For every triplet of first name, middle name, and last name. You are to print the full name in the following format 

```
1. <First Name 1> <Middle Initial 1>. <Last Name1>
2. <First Name 2> <Middle Initial 2>. <Last Name2>
3. <First Name 3> <Middle Initial 3>. <Last Name3>
```

The first line should be combined from the first name, middle name, and last name found on index 0 of every list, the second line should be combined from the names found on index 2 of every list and so on. 

The correct output should look like th following:
```
1. James T. Brown
2. Emma R. Davis
3. Mohammed Y. Garcia
4. Aisha M. Nguyen
5. Satoshi J. Singh
6. Yuki I. Ali
```


```python
first_names = ["James", "Emma", "Mohammed", "Aisha", "Satoshi", "Yuki"]
middle_names = ["Thomas", "Rose", "Yusuke", "Mei", "Javier", "Isabella"]
last_names = ["Brown", "Davis", "Garcia", "Nguyen", "Singh", "Ali"]

# Solution

appended_lists = zip(first_names, middle_names, last_names)
appended_lists = [f"{first} {middle[0]}. {last}" for first, middle, last in appended_lists]

i = 1
for names in appended_lists:
    print(f"{i}.", names)
    i += 1
        
    
```

    1. James T. Brown
    2. Emma R. Davis
    3. Mohammed Y. Garcia
    4. Aisha M. Nguyen
    5. Satoshi J. Singh
    6. Yuki I. Ali
    

### Challenge3: Full Names, Incomplete Data
In the scenario below you're still working on the same lists. But this time some names are missing. Missing names are represented by empty strings (`''`).

Similar to the previous task, print the combined names for every person. If the person is missing their first, middle or last name, do not print a line for the person. Skip to the next person instead. Make sure the numbering doesnt skip.

The correct print should look like the following

```
1. Sarah G. Jones
2. Liang Y. Li
3. Ahmed J. Khan
4. Priya M. Patel
```


```python
first_names = ["Sarah", "James", '', "Liang", "Sakura", "Ahmed", "Priya"]
middle_names = ["Grace", "Thomas", "Rose", "Yuki", '', "Jasmine", "Muhammad"]
last_names = ["Jones", '', "Davis", "Li", "Yamamoto", "Khan", "Patel"]

# Solution

i = 0
j = 1
for names in first_names:
    if names != "" and middle_names[i] != ""  and last_names[i] != "":
        print(f"{j}.", names, f"{middle_names[i][0]}.", last_names[i])
        j += 1
    i += 1
   

```

    1. Sarah G. Jones
    2. Liang Y. Li
    3. Ahmed J. Khan
    4. Priya M. Patel
    

### Challenge4: Qualitative Transformation

You are given a list of floats. Calculate the mean of all the floats in the list and store them to a variable.

Create a new list containing elements that correspond to qualitative transformations of each float in the list. 

If the float is less than the mean, its corresponding transformation is 'Low'. If the float is greater than the mean, its corresponding transformation is 'High'. If it is equal to the mean, its corresponding transformation is 'Average'. 

For example, given the following list of floats:
```
data = [1.2, 3.1, 0.2]
```
With a mean of 1.5 the new list should be
```
transformation = ['Low', 'High', 'Low']
```

Print the new list containing the transformations


```python
data = [1.2,3.1,0.2,-0.5,8.3,5.1,2.4]
# Solution

mean = sum(data)/len(data)
xform = []
for num in data:    
    if num < mean:
        xform.append("Low")
    elif num > mean:
        xform.append("High")
    else:
        xform.append("Average")    
print(xform)
```

    ['Low', 'High', 'Low', 'Low', 'High', 'High', 'Low']
    

###  Challenge5: Minimum Value

Given the list below, write python code to find the minimum (the minimum is the smallest value)


```python
data = [1.2,3.1,0.2,-0.5,8.3,5.1,2.4]
# Solution

min_num = data[0]

for num in data:
    if num < min_num:
        min_num = num

print(min_num)        

```

    -0.5
    

### CHallenge6: Sorting

Given the list below. Write python code to create a new list containing the same values but sorted from smallest to largest (smallest value should be in index 0, largest should be in the last position)


```python
data = [1.2,3.1,0.2,-0.5,8.3,5.1,2.4]
# Your code here
new_list = []

while data:
    min_val = min(data)
    new_list.append(min_val)
    data.remove(min_val)
    
print(new_list)

```

    [-0.5, 0.2, 1.2, 2.4, 3.1, 5.1, 8.3]
    


```python

```
