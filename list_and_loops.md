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

