## Introduction to Python

Just trying to get you familiarised with building blocks in Python!

The course materials are adapted from [this ](http://datacarpentry.org/python-socialsci/)[Data Carpentry lesson - Data Analysis and Visualization with Python for Social Scientists](https://datacarpentry.org/python-socialsci/)[.](http://datacarpentry.org/python-socialsci/) Please note that it is designed for participants with no programming experience.


## 1. Arithmetic Operators

- `+`: Addition
- `-`: Subtraction
- `*`: Multiplication
- `/`: Division
- `//`: Divides and rounds down to the nearest integer
- `%`: Modulo (the remainder after dividing)
- `**`: Exponentiation

```python
print(10 + 3) # 13

print(10 - 3) # 7

print(10 * 3) # 30

print(10 / 3) # 3.3333333333333335

print(10 // 3) # 3

print(10 % 3) # 1

print(10 ** 3) # 1000
```
Some operators are clever enough to also work with strings when it makes sense.

```python
# Repeating the strings by a given number of times
print('Hello' * 5) # 'HelloHelloHelloHelloHello'

# Adding strings together
print('Hello' + ' ' + 'NUS Libraries') # 'Hello NUS Libraries'
```



## 2. Booleans, Comparison Operators, and Logical Operators

### Comparison Operators

| Symbol | Operation                |
| ------ | ------------------------ |
| ==     | Equal To                 |
| !=     | Not Equal To             |
| >      | Greater Than             |
| <      | Less Than                |
| >=     | Greater Than or Equal To |
| <=     | Less Than or Equal To    |

```python
print(10 > 3) # True

print(10 < 3) # False

print(10 >= 3) # True

print(10 <= 3) # False

print(10 == 3) # False

print(10 != 3) # True
```

You can compare strings too. Please note that this is case-sensitive.

```python
print('Hello' == 'hello') # False

print('Hello' == 'Hello') # True
```



### Logical Operators

| **Logical Use** | **Operation**                                                |
| :-------------- | :----------------------------------------------------------- |
| `and`           | Checks if all provided statements are True                   |
| `or`            | Checks if at least one of the provided statements is True    |
| `not`           | Flips the boolean value from True to False or from False to True |

```python
print(10 > 3 and 10 > 5) # True

print(10 > 3 and 10 <= 5) # False

print(10 > 3 or 10 <= 5) # True

print(not 10 <= 5) # True
```



## 3. Types and Type Conversation

### Common data types

```python
print(type(168)) # <class 'int'>

print(type(168.0)) # <class 'float'>

print(type('680')) # <class 'str'>

print(type('NUS Libraries')) # <class 'str'>
```



### Type Conversion

- `int()`: converts a numeric string or a number to an integer number
- `float()`: converts a numeric string or a number to a floating point number
- `str()`: converts the specified value into a string

```python
# integer to string
print(str(168)) # '168'

# integer to float
print(float(168)) # 168.0

# float to string
print(str(168.0)) # '168'

# float to integer
print(int(168.0)) # 168

# float to integer
print(int(int(3.63))) # 3

# numeric string to integer
print(int('680')) # 680

# numeric string to float
print(float('680')) # 680.0
```



## 4. Variables

Below shows a simple example. "msg" is the variable name, and it holds the value "Hello, NUS Libraries!"

```python
# A simple example
msg = 'Hello, NUS Libraries!'

print(msg) # 'Hello, NUS Libraries!
```

### A few things to note
- Use only lowercase letters, numbers and underscores in your variable names.
  - Yes: my_height, fruits, student_number
  - No: my height, StudentNUM
- Do not use reserved words or built-in identifiers
  - Check out the lists of reserved words [here](https://www.w3schools.in/python-tutorial/keywords/)

```python
# A few more examples
this_number = 168

length = 168.0

width = '68'

height, weight = 123, 134
```



## 5. Strings

### Length
`len()` is a built-in function in Python that return the number of items in a container. For strings, it returns the number of characters in the string.

```python
print(len('Hello, NUS Libraries!')) # 21

print(len('Hi')) # 2
```



### Getting substring

```python
msg = 'Hello, NUS Libraries!'

# get the first character of the string msg, we start counting at 0
print(msg[0]) # 'H'

# get a portion of the string by indicating the start and end position
print(msg[7:10]) # 'NUS'

# leave the end position empty to have the string from a given point
print(msg[7:]) # 'NUS Libraries!'

# leave the start position empty to have the string until a given point
print(msg[:7]) # 'Hello, '

# you can use negative values to count from the end of the string
print(msg[-3:]) # es!
```



### String methods

**Functions vs. Methods**

- A **function** takes a set of arguments (can be more than one) as input using parentheses and produces output, e.g., `print(msg)`, `len(msg)`.
- A **method** works like a function, but it belongs to a particular type of object only. For example, `upper` is a string method. It can be applied to the string "hello" and transform it into "HELLO". However, it will not work on a list of strings, e.g., ['hello', 'hi']. Similarly, the `append` method that we will introduce later is a list method, so it can be applied to lists only. In contrast, the function `len()` can return the number of characters/items in both strings and lists. A method is applied to an object using dot notation : `object_name.method_name()`.


#### Text cases

```python
msg = 'Hello, NUS Libraries!'

# convert the word to lowercase
print(msg.lower()) # 'hello, nus libraries!'

# convert the word to uppercase
print(msg.upper()) # 'HELLO, NUS LIBRARIES!'

# convert the first character in each word to uppercase and remaining characters to lowercase
print(msg.title()) # 'Hello, Nus Libraries!'
```



#### Space trimming

```python
this_string = '  hihihihihi   '

# trim the leading and trailing spaces
print(this_string.strip()) # 'hihihihihi'
```



#### Replacing substring

It splits the given string into a list of strings by a given separator.

`string.replace(old, new, count)`

- old: the old substring that you want to replace
- new: the new substring that you want to replace the old substring with
- count: the number of times that you want to replace the old substring with the new substring (optional)

```python
msg = 'NUS NUS NUS NUS'

# replace all "NUS" in msg to "nus"
print(msg.replace('NUS', 'nus')) # 'nus nus nus nus'

# replace the first "NUS" in msg to "nus"
print(msg.replace('NUS', 'nus', 2)) # 'nus nus NUS NUS'
```



#### String split

It splits the given string into a list of strings by a given separator.

`string.split(separator, maxsplit)`

- separator: the specified separator that the string will be split at. If not provided, any white space will be used as the separator.
- maxsplit: the maximum number of times that the split should repeat (optional)

```python
date = '2019-08-16 04:10:05'

# split the string date by '-'
print(date.split('-')) # ['2019', '08', '16 04:10:05']

# split the string date by ':'
print(date.split(':')) # ['2019-08-16 04', '10', '05']

# split the string date by ':' and do it once only
print(date.split('-', 1)) # ['2019', '08-16 04:10:05']
```



#### Count
It returns the number of occurrences of a substring in the given string.  It is case-sensitive.
`string.count(substring,  start, end)`

- substring: the substring that you are looking at
- start: the starting index within the string where the search starts
- end: the ending index within the string where the search ends

```python
msg = 'Hello, NUS Libraries!'

# count the number of 'l' in the string msg
print(msg.count('l')) # 2

# count the number of 'l' in the string msg, starting from the 4th position
print(msg.count('l', 3)) # 1
```



#### Find

It returns the starting index of the substring (the first occurrence) if it is found in the given string. If it is not found, it returns -1. It is case-sensitive.
`string.find(substring, start, end)`

- substring: the substring that you are looking for
- start: the starting index within the string where the search starts (optional)
- end: the ending index within the string where the search ends (optional)

```python
msg = 'Hello, NUS Libraries!'

# find the position 'nus' in the string msg
print(msg.find('nus')) # -1

# find the position 'NUS' in the string msg
print(msg.find('NUS')) # 7

# find the position of 'l' in the string msg, starting from the 4th position
print(msg.find('l', 3)) # 3
```



## 6. Lists

<p style="font-size: 16px; ">A list is one of the most common data structures in Python. You can create a list with square brackets. It can be a mix of different data types.</p>
```python
list_of_mixed_data = ['NUS Libraries', 268, 168.0, True]
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']
```



### Indexing & Slicing

This works similar to getting a substring from strings.

The index of a list in Python starts from 0. To get the first element of a list, simply say `list[0]`.

Using slicing, you can pull multiple elements from the list based on their positions. For example, `list[1:3]` will return the 2nd and the 3rd elements in the list. It is important to remember that the slicing will include the lower index but not the upper index. 

```python
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']

# get the first element of the list
print(fruits[0]) # 'Apple'

# get multiple items in the middle of the list by indicating the start and end index
print(fruits[1:3]) # ['Pear', 'Peach']

# Leave out the start index to start at the beginning and stop at a given position
print(fruits[:4]) # ['Apple', 'Pear', 'Peach', 'Pineapple']

# Leave off the end index to return all of the elements to the end 
# and use a negative value to count from the end of the string
print(fruits[-2:]) # ['Pineapple', 'Durian']
```



### Mutability

Lists in Python are mutable. It means that we can change the object after it has been created.

```python
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']

# Now set the 3rd object of fruits to be "pineapple"
fruits[2] = 'Melon'

print(fruits) # ['Apple', 'Pear', 'Melon', 'Pineapple', 'Durian']
```



### Length 

```python
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']

# get the number of items in the list
print(len(fruits)) # 5
```



### sorted, max & min

- `sorted()`: It returns a copy of a list in ascending order, leaving the list unchanged.
- `max()`: It returns the largest element of the list.
- `min()`: It returns the smallest element of the list.

#### Sorting a list of numbers

```python
numbers = [1, 8, 99.0, 10, 152.8, 52]

# sort the numbers from smallest to largest
numbers_sorted = sorted(numbers)
print(numbers) # [1, 8, 99.0, 10, 152.8, 52]

print(numbers_sorted) # [1, 8, 10, 52, 99.0, 152.8]

# return the largest number from the list
print(max(numbers)) # 152.8

# return the smallest number from the list
print(min(numbers)) # 1
```



#### Sorting a list of strings

```python
fruits = ['Apple', 'Lychee', 'Peach', 'Pineapple', 'Durian']

# sort the list of strings alphabetically
fruits_sorted = sorted(fruits)
print(fruits_sorted) # ['Apple', 'Durian', 'Lychee', 'Peach', 'Pineapple']

# return the string element comes last in alphabetical order
print(max(fruits)) # 'Pineapple'

# return the string element comes first in alphabetical order
print(min(fruits)) # 'Apple'
```



###  in OR not in

```python
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']

# Check whether there is an element "Apple" in the list
print('Apple' in fruits) # True

# Check whether there is an element "apple" in the list
print('apple' in fruits) # False

# Check whether there is no "Apple" in the list
print('Apple' not in fruits) # False
```



### String methods

#### pop

It removes and displays an element from a list by the given index. If the index is not stated, the last element will be removed.

`list.pop(index)`

- index: the index of the element that you want to display and remove from the list

```python
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']

# remove and the display the last item of the list
print(fruits.pop()) # 'Durian'
print(fruits) # ['Apple', 'Pear', 'Peach', 'Pineapple']


# remove and the display the 3rd item of the list
print(fruits.pop(2)) # 'Peach'
print(fruits) #['Apple', 'Pear', 'Pineapple']
```



#### join

<p style="font-size: 15px;">It returns a string consisting of the list elements joined by a given separator.</p>
`list.join(separator)`

- separator: the specified separator.

```python
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']

# join the list of fruits by the separator '; '
'; '.join(fruits)
# 'Apple; Pear; Peach; Pineapple; Durian'
```



### append
<p style="font-size: 15px;">It adds and element to the end of a list.</p>
`list.append(item)`

- item: the item to add

```python
# create an empty list fruits
fruits = []

# add an item "Apple" to the list
fruits.append('Apple')
print(fruits) # ['Apple']

# add another item "Pear" to the end of the list
fruits.append('Pear')
print(fruits) # ['Apple', 'Pear']
```



## 7. Dictionaries

Dictionaries are another data structure. You can think of it as a list of key:value pairs. It will make it possible to recall a value by its key instead of using an index number.<br>Below is an example of a dictionary.

### Accessing a value
You can look up values using square brackets that enclose the key.

```python
fruits_color = {
    'apple': 'red',
    'peach': 'pink',
    'grape': 'purple'
}

# get the value of "apple" from the dictionary
print(fruits_color['apple']) # 'red'
```



### Mutability

Similar to lists, dictionaries in Python are mutable. It means that we can change the value of an object in the dictionary after it has been created.

```python
fruits_color = {
    'apple': 'red',
    'peach': 'pink',
    'grape': 'purple'
}

# change the value of "apple" to "green"
fruits_color['apple'] = 'green'
print(fruits_color) # {'apple': 'green', 'grape': 'purple', 'peach': 'pink'}

# add a new element "pineapple" and set the value to "yellow"
fruits_color['pineapple'] = 'yellow'
print(fruits_color) # {'apple': 'green', 'grape': 'purple', 'peach': 'pink', 'pineapple': 'yellow'}
```



### in OR not in

For lists, we use `in` to check whether an element exists. For dictionaries, `get` method can be used. It returns the value of the element if it exists. Otherwise, None will be returned.
```python
fruits_color = {
    'apple': 'red',
    'peach': 'pink',
    'grape': 'purple'
}

# look up the element "peach"
print(fruits_color.get('peach')) # 'pink'

# look up the element "mango"
print(fruits_color.get('mango')) # None
```



## 8. Conditional Statements

```python
# is 10 larger than 5?
if 10 > 5:
    print('Yes')

# 'Yes'
```
```python
# is 10 equal to 5?
if 10 == 5:
    print('Yes')
else:
    print('No')

# 'No'
```


```python
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']

# check if there is a "Watermelon" in the list
if 'Watermelon' in fruits:
    print('Yes')
else:
    print('No')
    # add the element 'Watermelon' to the list if it doesn't exist
    fruits.append('Watermelon')  
    print(fruits)

# 'No'
# ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian', 'Watermelon']
```



## 9. For Loops and While Loops

### For Loops

A **for loop** is used to iterate or do something repeatedly.

```python
fruits = ['Apple', 'Pear', 'Peach', 'Pineapple', 'Durian']

# Looping through all elements in the list
for fruit in fruits:
    print(fruit)

# 'Apple'
# 'Pear'
# 'Peach'
# 'Pineapple'
# 'Durian'
```

```python
# Looping through all elements in the list
for num in [1, 5, 19, 28]:
    # add 8 to each element
    print(num + 8)

# 9
# 13
# 27
# 36
```



###  While loop

**For loops** are used when we know the exact number of times that the loop should repeat. If the loop is supposed to repeat an unknown number of times until specific conditions are met, we use **while loops** instead.

```python
numbers = [2, 8, 19, 11, 2, 19, 1, 5]
numbers_add = []

# move the elements from the numbers to numbers_add (from left to right) until the sum of numbers_add reach 55 or more
while sum(numbers_add) <= 55:
    numbers_add.append(numbers.pop(0)) 
    
print(numbers_add)
print(sum(numbers_add))

# [2, 8, 19, 11, 2, 19]
# 61
```





## 10. Defining a Function

- **Function Header**
  - The function header always starts with a "def", which indicates that this is a function definition.
  - Followed by the "def", we should have the function name, e.g., "get_len" in the example below
  - After the name of the function, there are parentheses that include the arguments, multiple arguments are separated by commas.
  - The header always ends with a colon ":".

- **Function Body**

  - The body of a function is the code indented (4 spaces) after the header line.

  - The function body usually includes a return statement to return the output value from the function. If there is no return statement, the function simply returns None.
```python
def get_text_lenghth(text):
    """
    This function returns the length of a given string
    INPUT:
       (str) text: the given string
    OUTPUT:
       (int) textLen: the length of the text
    """
    text_lenghth = len(text)
    return  text_lenghth
    

print(get_text_lenghth('I love NUS Libraries'))
# 20
```

```python
def cuboid_volume(length, breadth, height):
    """
    This function returns the volume of a cuboid based on the length, breadth, height given.
    INPUT:
       (int/float) length: the length of the cuboid
       (int/float) breadth: the breadth of the cuboid
       (int/float) height: the height of the cuboid
    OUTPUT:
       (int/float) the volume of the cuboid
    """
    return length * breadth * height

print(cuboid_volume(2, 3, 4))
# 24
```
