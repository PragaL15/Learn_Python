### List and Loops based questions in python

1. To create a list and print item in 0th and last index.

```python
list1 = ["apple","banana","oranges","cherry"]
print(f"This is 0th index - {list1[0]},This is last item {list1[-1]}")
```
- `Negative Index` - start from the end
---
2. To get Input for a Fixed-Length List and print them.

```python

my_list = []
for i in range(3):
    item = input()
    my_list.append(item) 
print("Your list is:", my_list)
```
output
```
go
grt
run
```
**if I want to get user input in a single line**

```python

my_list = []
user_inp = input()
item = user_inp.split()
my_list.append(item)
print("Your list is:", my_list)
```
- using `append()` will create a nested list line [["app","web"]]
- using `extend()` will add each item in the list as a seperate item in the list.


---
3. Check if the particular word is in the list or not.

```python

my_list = []
user_inp = input()
item = user_inp.split(",")
my_list.extend(item)
if "go" in my_list:
  print("true")
else:
  print("false")
```
- In this we should use only `extend()` as The `in` operator checks for membership at the top level of `my_list`, not inside nested lists.
```
i/p: start,set,go
o/p: true
```
---
4. To get the number input from the user and the display the list

```python
my_list = []
user_inp = input()
item = [int(num) for num in user_inp.split(" ")]
my_list = item
print(my_list)
```
- Why do we use typeconversion ?
`input()` function in Python always returns the user's input as a `string` so to convert the string into int we need type conversion.

---

5. I need to replace the value from the list with other value.

```python

my_list = []
item = input().split(" ")
my_list = item
my_list[1] = "orange"
print(my_list)
```
- this will replace the value of the particular index without changing the index of others
---
6. Need to replace the range of value from the list.

```python
my_list = []
item = input().split(" ")
my_list = item
my_list[1:3] = ["orange","melon"]
print(my_list)
```
- I/p -> apple banana cherry tadcgv and o/p ->['apple', 'orange', 'melon', 'tadcgv']

---
7. Insert a value into the list.

```python

my_list = []
item = input().split(" ")
my_list = item
my_list.insert(1,"pineapple")
print(my_list)
```
- this will insert the value at gvn index and move the word in that index to the next index , this will not replace the value rather it adds the value to list.

---
8. Add value to list by using append()

```python

my_list = []
item = input().split(" ")
my_list = item
my_list.append("pineapple")
print(my_list)
```
- this will add the value at the end of the list.
---
9. Add the value to list using the extend().

```python
my_list = []
item = input().split(" ")
my_list = item
my_list.extend("pineapple")
print(my_list)
```
- The `extend()` method is used to add each character of the argument (in this case, the string "pineapple") individually to `my_list`.
- `extend()` treats it as a sequence of characters and `adds each character separately` to my_list.

---
10. Add two list and print the combine list.

```python

my_list = []
my_list2 =[]
item = input().split(" ")
my_list = item
item2 = input().split(" ")
my_list2=item2
my_list.extend(my_list2)
print(my_list)
```
- Now my_list is has the combined list that includes the `my_list2`

---
11. To remove the first occurance of the word from the list and print the list.

```python

my_list = []
my_list2 = []
item = input().split(" ")
my_list = item
item2 = input().split(" ")
my_list2 = item2
for element in my_list2:
    if element in my_list:
        my_list.remove(element)
print(my_list)

```
---

12. If I want to remove an element from certain index.

```python 
my_list = []
my_list2 = []
item = input().split(" ")
my_list = item
my_list.pop(2)
print(my_list)
```
**or**
```python
my_list = []
my_list2 = []
item = input().split(" ")
my_list = item
del my_list[0]
print(my_list)
```

- This will remove the word from the particular index.
---
13. 