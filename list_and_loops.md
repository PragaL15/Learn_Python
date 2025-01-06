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

**or**
```python
my_list = []
my_list2 = []
item = input().split(" ")
my_list = item
for my in my_list:
 print(f"{my} ",end="")
```

**or**

- Print using the `range()` in the for loop.
```python
my_list = []
my_list2 = []
item = input().split(" ")
my_list = item
for my in range(len(my_list)):
 print(f"{my_list[my]} ",end="")
```
**or**
- Using the while loop.
```python
my_list = []
my_list2 = []
item = input().split(" ")
my_list = item
i=0
while i < len(my_list):
 print(f"{my_list[i]} ",end="")
 i+=1
```
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
- This will remove the word from the particular index.

**or**

```python
my_list = []
my_list2 = []
item = input().split(" ")
my_list = item
del my_list[0]
print(my_list)
```
- By using the `del` we could delete the list completly.
---
13. To make an empty list.

**using `clear()`**:
```python
my_list = []
my_list2 = []
item = input().split(" ")
my_list = item
my_list.clear()
print(my_list)
```
---
#### List Comprehension in Python

1. Basic List Comprehension by getting input from user and multiply the number by 2 and print their output.

```python
my_list =[]
user = input()
my_list=[int(num) for num in user.split(" ")]
squares = [x*2 for x in my_list]
print(squares)
```
---
2. Along with for loop use the if condition also and print the results which passes the condition.

```python
my_list =[]
user = input()
my_list=[int(num) for num in user.split(" ")]
squares = [x*2 for x in my_list if x%3==0 and x%4==0]
print(squares)
```
---
3. Having both `if` and `else` statements on same code.

```python
my_list =[]
user = input()
my_list=[int(num) for num in user.split(" ")]
squares = ["Even" if x%2==0 else "odd" for x in my_list]
print(squares)
```
---
4. Nested loop example

```python
my_list =[]
user = input()
my_list=[int(num) for num in user.split(" ")]
squares = [(x,y) for x in range(1,5) for y in range(1,3) if(x+y)%2==0]
print(squares)
```
- In this range(1,5) - it includes 1,2,3,4.
- the first for loop is outer and next is inner loop.

---

### Loops questions

1. Fibonacci series , sum and the nth term.

```python
def fibo(n):
  if n<=1:
    return n 
  return fibo(n-1)+fibo(n-2)

num = int(input())
if(num<=0):
 print("Invalid Input")
else:
  fib_series = [fibo(i) for i in range(num)]
  nth = fib_series[-1]
  sum_total = sum(fib_series)
  print(f"Fibonacci series:{fib_series}")
  print(f"{nth}")
  print(f"{sum_total}")
```
---
2. To find the next five prime numbers starting from the given number .

```python
def isPrime(n):
  if n<=1:
    return False 
  for i in range(2, int(n**0.5)+1):
    if n%i==0:
      return False 
  return True 
      

n = int(input())
start =0
count=0
nextNum = start+1
while 5>count:
   if isPrime(nextNum):
     print(nextNum)
     count+=1
   nextNum+=1 
```
---
3. To find if the given is prime num or composite num

```python
def isPrime(n):
  if n<=1:
    return False 
  for i in range(2, int(n**0.5)+1):
    if n%i==0:
      return False 
  return True 
      
num = int(input())
if isPrime(num):
 print("Prime number")
else:
 print(f"Composite number")
```
---
4. To print the sum of series of the given num and number of terms is also gvn 
ex: 3 4 --> 3+33+333+3333 = 3702

```python
def sumSeries(n,count):
  if n<=0:
    return 0
    
  sumNum = 0
  res = 0
  place = 1;
  for i in range(1,count+1):
      res = n*place + res
      sumNum+=res
      place*=10
  return sumNum
      
num = int(input())
count = int(input())
result = sumSeries(num,count)
print(result)
```
---
5. If the divison's sum is equal to the given number , print it's equal number else print not an equal number

```python
num = int(input())
sumNum =0
for i in range(1,num):
  if num%i==0:
   sumNum+=i

if(num==sumNum):
 print("equal number")
else:
  print("Not an equal number")
```
---
6. Check if given is Abundant num or not ( if the sum of divisors are greater than the num)

```python
num = int(input())
sumNum =0
for i in range(1,num):
  if num%i==0:
   sumNum+=i

if(num<sumNum):
 print("Abundant number")
else:
  print("Not an Abundant number")
```
---
7. Counted the number of leap and non-leap year in nxt decade.
ex: 2020 o/p leap year count-2 and non-leap year count-8

```python
year= int(input())
LeapCount =0
NonLeapCount = 0

for i in range(year+1,year+10):
  if (i%4==0 and i%100!=0) or i%400==0:
   print(f"{i} is leap year")
   LeapCount+=1
   year+=1 
  year+=1 
  
print(f"leap year count {LeapCount}")
NonLeapCount = 10- LeapCount
print(f"Non leap year count {NonLeapCount}")
```
---
8.  Geometric Series Sum Calculator.
ex: inp = 5
Series: 
1
+
0.5
+
0.25
+
0.125
+
0.0625
1+0.5+0.25+0.125+0.0625
Sum: 
1.9375
1.9375
```python
def geometric_series_sum(n):
    if n <= 0:
        return 0.00 
    sum_series = 0.0
    term = 1.0  
    for _ in range(n):
        sum_series += term 
        term /= 2  
    return round(sum_series, 2)  
n = int(input())
result = geometric_series_sum(n)
print(f"The sum of the series is: {result:.2f}")
```
- If the loop variable is not needed inside the loop (e.g., you’re not using the index for any calculations), using `_` makes the code cleaner and signals that the index is irrelevant.
- In this, `n = int(input())` int in this is very important as we'll get type error as we can't use `<,>,=` on strings directly.
---
9. Sum of Squares of N Natural Numbers
i/p = 5 o/p = 55 (1+4+9+16+25)

```python
num = int(input())
sumNum =0
term=0
for i in range(1,num+1):
  term = i*i
  sumNum+=term
if num<0:
 print("Invalid Input")
else:
 print(f"{sumNum:}")
```
---
10. Harmonic series 
```python
n = int(input()) 
sum_series = 0.0
for i in range(1, n + 1):
        sum_series += 1 / i  
if n<0:
  print("Invalid input")
else:
  print(f"The sum of harmonic series is: {sum_series:.2f}")
```
---
11. Count the number of digits in the given number.

```python
n = int(input()) 
n = abs(n)
count =0
while n!=0:
      count+=1 
      n//=10
print(f"The count of digits is {count}")
```
---
12. Print the square pattern

```python
n = int(input()) 
count =0
if n<=0:
  print("Invalid Input")
else:
  for i in range(1,n+1):
    for j in range(1,n+1):
      print("#",end=" ")
    print()
```
---
13. Pyramid pattern 

```python
n = int(input()) 
num=1
if n<=0:
  print("Invalid Input")
else:
  for i in range(1,n+1):
    for j in range(1,i+1):
      print(num,end=" ")
      num+=1
    print()
  ```
---

14. Swap the first and last digit of the given number.

```python
n = (input()) 
len1=len(n)
first = n[0]
last = n[len1-1]
swap = last + n[1:-1] + first
swapNum = int(swap)
if swapNum<=0:
  print("Invalid Input")
else:
  print(swap)
```
---
15. Perfect cubes of the consecutive 3 numbers from `n` if it's positive else print Invalid input.

```python
n = int(input()) 
cu=0
if n<=0:
  print("Invalid Input")
else:
  for i in range(n,n+3):
    cu = pow(i,3)
    print(cu)
```
---
16. Convert the intergers into roman numerals from range of 1 to 40.

```python
def int_to_roman(n):
    roman_map = [
        (40, 'XL'), (30, 'XXX'), (20, 'XX'), (10, 'X'), 
        (9, 'IX'), (5, 'V'), (4, 'IV'), (1, 'I')
    ]
    
    roman_numeral = ""
    for value, symbol in roman_map:  
        while n >= value:
            roman_numeral += symbol
            n -= value
    return roman_numeral

n = int(input())
if 1 <= n <= 40:
    print(f"{n} -> {int_to_roman(n)}")
else:
    print("Please enter a number between 1 and 40.")
```
---
17. Sum of N odd and Even numbers ex: 5 means 1+3+5=9(odd) and 2+4 = 6.

```python
n = int(input())
odd =0
evn =0
for i in range(1,n+1):
 if i%2==0:
  evn+=i
 else:
  odd+=i
print(odd,evn)
```
---
18. Narcissist number or not 

```python
n =(input())
len1 = len(n)
temp =int(n)
num = int(n)
sum1=0
while(temp!=0):
  rem = temp%10
  res = pow(rem,len1)
  sum1+=res
  temp//=10
  
if num==sum1:
 print("Narciss")
else:
  print("Not Narciss")
```
- `temp//=10` - correct operation to remove the last digit of an integer is integer division if we used `temp/=10` then we will not get intended output.

19. Digital sum of a number

```python
n =(input())
num = int(n)
sum1=0
while num>0 or sum1>9:
    if num==0:
      num=sum1
      sum1=0
    sum1+=num%10
    num//=10
  
print(sum1)
```
---
20. Alphabet pattern 
```
A 
B B 
C C C 
```
```python
n =(input())
num = int(n)
ch = 'A'
for i in range(1,num+1):
  for j in range(1,i+1):
    print(f"{ch} ",end="")
  ch = chr(ord(ch) + 1)
  print()
```
---
21. Print the next 5 concecutive palindrome from the given number.

```python
def isPalindrom(n):
  temp=n 
  digit =0
  while temp!=0:
    rem = temp%10
    digit = digit*10 + rem
    temp//=10
  return n==digit
  
num = int(input())
count = 0 
if num<0:
  print("Invalid input")
else:
  while count<5:
    num+=1
    if isPalindrom(num):
     print(f"{num} ")
     count+=1
```
---
22.  it's a palindrome and sum all palindrome
numbers upto given number as output.

```python
def isPalindrom(n):
  temp=n 
  digit =0
  while temp!=0:
    rem = temp%10
    digit = digit*10 + rem
    temp//=10
  return n==digit
  
num = int(input())
sum1 = 0 
if num<0:
  print("Invalid input")
else:
  for i in range(1,num+1):
     if(isPalindrom(i)):
       sum1+=i
  print(sum1)
```
---

23. 
```
5 
5 10 
5 10 15 
5 10 15 20 
```

```python
num = int(input())
sum1 = 0 
if num<0:
  print("Invalid input")
else:
  for i in range(1,num+1):
     for j in range(1,i+1):
        print(f"{j*5} ",end="")
     print()
```
---
24. To print the prime number star pattern ,  it iterates over each row and checks whether the row number is prime or not. If it's prime, it prints '*' for that row.

```python
def isPrime(n):
  if n<=1:
    return False
  for i in range(2,int(n**0.5)+1):
    if n%i==0:
      return False
  return True
  
row = int(input())
for i in range(1,row+1):
  if isPrime(i):
    print('* ' *i)
```
i/p - 8
o/p 
```
* * 
* * * 
* * * * * 
* * * * * * * 
```
---
25. Finding the LCM and GCD.

```python
def gcdcheck(num1,num2):
 while num2!=0:
   temp = num2
   num2=num1%num2
   num1=temp
 return num1

def lcmcheck(num1,num2):
  gcd = gcdcheck(num1,num2)
  lcm = (num1*num2)//gcd
  return lcm
  
num1 = int(input())
num2 = int(input())
lcm = lcmcheck(num1,num2)
print(lcm)
```
---
26. . The
program should then simulate handshakes between each pair of people and Count the total number
of handshakes that occur. Print out the total number of handshakes.

```python
def handshake(n):
 if n<=1:
   return 0
 return n* (n-1) // 2
num = int(input())
total = handshake(num)
print(total)
```
---
27. To calculate the sum of series The students are tasked with Craft, a program that calculates the sum of the series 1 - (x^2)/2! +
(x^4)/4! - (x^6)/6! + ... The program should prompt the user to input the value of 'x' and the number
of terms 'n' in the series.


```python
import math 
def cal_sum_series(x,n):
  series_num=1 
  sign = -1
  for i in range(1,n):
   term = (x**(2*i))/math.factorial(2*i)
   series_num+=sign*term
   sign*=-1
  return series_num

x = float(input())
y = int(input())
if y <= 0:
    print("The number of terms must be a positive integer.")
else:
    result = cal_sum_series(x, y)
    print(f"The sum of the series is: {result:.2f}")
  ```
---
28. Craft a program that takes an integer as input and performs the following operation using only the
bitwise XOR operator:
- If the input number is even, divide it by 2.
- If the input number is odd, multiply it by 3 and add 1.
- Continue this process until the resulting number is 1. Count and return the number of steps
taken to reach 1.

```python
def collatz_steps(n):
    if n <= 0:
        return "Input must be a positive integer."
   while n != 1:
        if n & 1 == 0:  # If n is even
            n ^= (n >> 1)  # Simulate division by 2 using XOR
        else:  # If n is odd
            n = (n ^ (n << 1)) + 1  # Simulate n = n * 3 + 1 using XOR
        steps += 1
    return steps
num = int(input())
if num > 0:
    result = collatz_steps(num)
    print(f"Number of steps to reach 1: {result}")
else:
    print("Please enter a positive integer.")
```
---
29. Print if it's automorphic number or not.
    ```python
    def is_automorphic(num):
    square = num ** 2
    return str(square).endswith(str(num))
    num = int(input("Enter a number: "))
    if num < 0:
        print("Invalid Input")
    else:
        if is_automorphic(num):
            print(f"{num} is an Automorphic Number.")
        else:
            print(f"{num} is not an Automorphic Number.")
 
  ```
