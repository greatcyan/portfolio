# More about sequences
## `list`/`tuple`/`string` slicing

Given a python list, tuple, or string you can easily extract a **slice** using advanced indexing. A slice is a list/tuple/string formed from the same elements of a given list. For example you can extract a slice that contains first 3 elements of a list using the following indexing:


```python
items = [0,1,2,3,4,5,6,7,8]
items[0:3]
```




    [0, 1, 2]



The slice `items[i:j]` corresponds to the list containing the elements from position `i` until `j-1`. In the case above, with the index `[0:3]` we extract the elements from position 0 until position 3-1. Here are some more examples


```python
items[0:4]
```




    [0, 1, 2, 3]




```python
items[2:2]
```




    []




```python
items[3:-1]
```




    [3, 4, 5, 6, 7]



If you omit the first index in the slice by default python starts extracting from the first element. On the other hand if you omit the second index in the slice, by default python will extract up to the last element.


```python
items[:2]
```




    [0, 1]




```python
items[:4]
```




    [0, 1, 2, 3]




```python
items[2:]
```




    [2, 3, 4, 5, 6, 7, 8]




```python
items[:]
```




    [0, 1, 2, 3, 4, 5, 6, 7, 8]



If you add a third index in the slice (e.g. `items[i:j:k]`) python will skip `k-1` elements when extracting


```python
items[1:6:2]
```




    [1, 3, 5]




```python
items[1:6:1]
```




    [1, 2, 3, 4, 5]




```python
items[::3]
```




    [0, 3, 6]




```python
items[::-1]
```




    [8, 7, 6, 5, 4, 3, 2, 1, 0]




```python
items[1::2]
```




    [1, 3, 5, 7]



Slicing works for tuples and strings as well


```python
coords = 0,1,2,3,4,5

coords[1:4:2]
```




    (1, 3)




```python
word = 'sequences'

word[2:7:2]
```




    'qec'



Take note that just like item retrievel, slicing does not change the value of the original sequence. This is the reason why slicing works on immutable types like tuples and strings. Slicing a sequence creates a new value and the original value is unaffected


```python
items = [0,1,2,3,4,5,6,7,8]
print(items[0:3])
print(items)
```

    [0, 1, 2]
    [0, 1, 2, 3, 4, 5, 6, 7, 8]
    

## Some more sequence related functions

Here are functions related to sequences that are can be helpful for us

### `zip()` 

The `zip()` accepts n sequences and combines them together like a zipper. The first element of the zipped sequence is a tuple containing the first elements of all the sequences, the second element of the zipped sequence is a tuple containing the second elements of all the sequence and so on until one of the sequences runs out of elements.

The value returned by the `zip()` function is a zip object. This object has to be coerced into the correct sequence type first so that it can be used


```python
tuple(zip([0,1,2,3,4],(0.0,0.1,0.2,0.3),'xyz'))
```




    ((0, 0.0, 'x'), (1, 0.1, 'y'), (2, 0.2, 'z'))




```python
list(zip([0,1,2,3,4],(0.0,0.1,0.2,0.3),'xyz'))
```




    [(0, 0.0, 'x'), (1, 0.1, 'y'), (2, 0.2, 'z')]



### `enumerate()`

The `enumerate()` function zips a sequence with its indices. Just like `zip()`, `enumerate()`'s result should be cast to the correct sequence type


```python
tuple(enumerate('abcde'))
```




    ((0, 'a'), (1, 'b'), (2, 'c'), (3, 'd'), (4, 'e'))



### `range()`

The `range()` function helps us create sequences given a range of values. For example, if we want to create a list of integers from 1 to 10, we can use `range()` as such:


```python
list(range(1,11)) #the results of range() must be coerced into the correct sequence type
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]



A tuple of elements from 100 to 1000 with each with each element increasing by 100 each:


```python
tuple(range(100,1001,100)) # we write 1001 as the range end since python always excludes the range end
```




    (100, 200, 300, 400, 500, 600, 700, 800, 900, 1000)



if we pass one arguments to `range()` python will start as zero and end at the passed argument minus 1:


```python
list(range(5))
```




    [0, 1, 2, 3, 4]



The `range()` function is also the most efficient way of creating simple `for` loops:


```python
for i in range(10,0,-1):
    print(i)
```

    10
    9
    8
    7
    6
    5
    4
    3
    2
    1
    

# Comprehension

Python also allows us to quickly create sequences from for loops. This is done through sequence **comprehension**. Comprehension works by collecting the results of a for loop into a list. For example the code below stores the squares of a list of integers into the list `newList`:


```python
newList = []
for elem in [1,2,3,4]:
    newList.append(elem*elem)

newList
```




    [1, 4, 9, 16]



This code can be summarized using comprehension as follow:


```python
newList = [elem*elem for elem in [1,2,3,4]]
```

This helps us quickly create populated sequences just by describing the elements in a for loop


```python
tuple(float(i) for i in range(10)) #without the tuple() coercion, a comprehension will result in a generator object
```




    (0.0, 1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0)




```python
{key:val for key,val in zip('abcd',range(4))}
```




    {'a': 0, 'b': 1, 'c': 2, 'd': 3}



## Sets

One more datatype we missed in python is the set dataype. A `set` in python is similar to sets in math. Sets do not guarantee the order of the elements, and unlike lists or tuples, it's values cannot repeat. Sets are created by surrounding a sequence of expressions in curly braces (`{}`)


```python
values = {'a','b','c','d','a','d'}
print(values)
print(len(values))
```

    {'a', 'd', 'c', 'b'}
    4
    

> Notice how duplicated values are ommited when sets are evaluated.

Python sets can also be operated on like mathematical sets. We can perform, union, intersection, and difference


```python
values.union({'c','d','e','f'})
```




    {'a', 'b', 'c', 'd', 'e', 'f'}




```python
values.intersection({'c','d','e','f'})
```




    {'c', 'd'}




```python
values - {'c','d','e','f'}
```




    {'a', 'b'}



Sets also support `for` loops and comprehensions. But be wary when using them in for loop, because the order of elements of a set may not be what you expect:


```python
for elem in {5,4,3,2,1,0,1,2}:
    print(elem)
```

    0
    1
    2
    3
    4
    5
    


```python
{i for i in range(10,1,-1)}
```




    {2, 3, 4, 5, 6, 7, 8, 9, 10}




```python

```
