# Python Tips 
### Data Structures
---
| Type          | mutable?      | ordered?    |
| ------------- |:-------------:| ----------: |
| List          | mutable       | ordered     |
| Tuple         | immutable     | ordered     |
| Set           | mutable       | not ordered |
| Dictionary    | mutable       | not ordered |
| String / Int  | immutable     |             |

### [List]
---
##### Sorting
```python
arr.sort(key=len, reverse=True)              # Sorts by length, from longest to shortest
arr.sort(key=lambda x: len(x), reverse=True) # Utilizing lambda

arr.sort(key=lambda x : x[0])                # [(10,15),(3,4),(5,11)] -> [(3,4),(5,11),(10,15)]

random.shuffle(nums)                         # randomly shuffles array
```

##### Searching
```python
max(arr,key=len)                             # Find the longest element in list

for i in range(len(nums)-1,-1,-1)            # Following two are equivalent
for i in reversed(range(len(nums))
```

##### Multiple Assignment
```python
results = [1] * 10                         
results[0:10:2] = [0]*len(results[0:10:2])  # [0,1,0,1,0,1,0,1,0,1]
```

### {Dictionary}
---
##### Searching
```python
max(counter.keys(), key = counter.get)     # Find the highest value out of keys
```

### [Other Data Structures]
---
##### Queue
```python
queue = collections.deque([1,2,3])
queue.append(4)
queue.popleft()
```

##### Min Heap
```python
arr = []
for num in nums:
    heapq.heappush(arr,num)
    heapq.heappop(arr)
```

### "String"
---
##### Replace / Find / Count
```python
s = s.replace("h","w",3)      # Creates a copy of string and replaces first 3 "h"s to "w"
s.find("ll",5)                # Returns the index of where "ll" is in string after index 5
s.lower().count("e")          # Creates a copy as lowercases and then counts number of "e"s
```


##### Operations
```python
s.capitalize()          # First letter is capitalized
s.isalnum()             # Checks alphanumeric character
s.isalpha()             # Checks alphabet character
s.isdecimal()           # Checks decimal character
s.isnumeric()           # Checks numeric
```

### Python Things
---
##### Pythonic
```python
# Step 1
while p1 != p2:
    if p1 != None:
        p1 = p1.next
    else:
        p1 = headB
    if p2 != None:
        p2 = p2.next
    else:
        p2 = headA

# Step 2
while p1 != p2:
    p1 = p1.next if p1 != None else headB
    p2 = p2.next if p2 != None else headA

# Step 3
while p1 != p2:
    p1 = p1.next if p1 else headB   # p1 = headB if not p1 else p1.next
    p2 = p2.next if p2 else headA   # p2 = headA if not p2 else p2.next
```

##### Multiple Inheritance
```python
class ArcticBear(Arctic, Bear, Land):
```

##### Split / Join
```python
strs = "hello there"    
strs = strs.split(" ")              # ["hello","there"]
strs = " ".join(strs)               # "hello there"
```

##### Zip
```python
a = [1,2,3] 
b = [4,5,6]
for i in zip(a,b):
    print(i)     # [(1,4),(2,5),(3,6)]
```

##### Map
```python
nums = [1,2,3,4]
k = map(lambda x : x**2, nums)
print(list(k))     # [1,4,9,16]
```

##### *
```python
board = [[1,2,3],[4,5,6],[7,8,9]]
*board                               # unpacks values
zip(*board)                          # zip unpacked values
def rotate(board):
    board[:] = zip(*board)           # must dereference as board[:], think about stack
    board[:] = map(list,zip(*board)) # converts the tuples to lists
```

##### Comparator
```python
array.sort(cmp = comparator)                       # python
array.sort(key = functools.cmp_to_key(comparator)) # python3
```

### Logic Operations / Bit Manipulation 
---
##### Boolean Logic
```python
sign = (x>0) - (x<0)                  # Can easily find sign
sign = (x<0) == (y<0)                 # Can easily compare signs 
sign * random_num * (random_num<500)  # Get result only if random_num is below 500
```

##### int vs integer division
```python
-5 // 2 = -3       # looks at left integer on number line 
int(-5//2) = -2    # looks at integer closer to zero
```

##### Bitwise Comparison
```python
~5                       # Not
5&3                      # And
5|3                      # Or 
5^3                      # Xor 
5^3^5 = 5^5^3 = 0^3 = 3  # Commutative
a&0xffffffff             # Mask to unsigned integer
```

##### Changing integer to binary
```python
bin(x)    # Returns integer x as a string of binary numbers
```