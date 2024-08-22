# Week 4 Programming Assignment

- Write three Python functions as specified below. Paste the text for all three functions together into the submission window. Your function will be called automatically with various inputs and should return values as specified. Do not write commands to read any input or print any output.
- You may define additional auxiliary functions as needed.
- In all cases you may assume that the value passed to the function is of the expected type, so your function does not have to check for malformed inputs.
- For each function, there are normally some public test cases and some (hidden) private test cases.
- "Compile and run" will evaluate your submission against the public test cases.
- "Submit" will evaluate your submission against the hidden private test cases. There are 10 private test cases, with equal weightage. You will get feedback about which private test cases pass or fail, though you cannot see the actual test cases.
- Ignore warnings about "Presentation errors".

## Write a Python function frequency(l) that takes as input a list of integers and returns a pair of the form (minfreqlist,maxfreqlist) where
- minfreqlist is a list of numbers with minimum frequency in l, sorted in ascending order
- maxfreqlist is a list of numbers with maximum frequency in l, sorted in ascending order
## Here are some examples of how your function should work.

```bash
  >>> frequency([13,12,11,13,14,13,7,11,13,14,12])
([7], [13])

>>> frequency([13,12,11,13,14,13,7,11,13,14,12,14,14])
([7], [13, 14])

>>> frequency([13,12,11,13,14,13,7,11,13,14,12,14,14,7])
([7, 11, 12], [13, 14])
```

### Solution :

```python
def frequency(l):
    freq = {}
    for num in l:
        if num in freq:
            freq[num] += 1
        else:
            freq[num] = 1

    min_freq = min(freq.values())
    max_freq = max(freq.values())

    minfreqlist = sorted([num for num, count in freq.items() if count == min_freq])
    maxfreqlist = sorted([num for num, count in freq.items() if count == max_freq])

    return (minfreqlist, maxfreqlist)
```

## An airline has assigned each city that it serves a unique numeric code. It has collected information about all the direct flights it operates, represented as a list of pairs of the form (i,j), where i is the code of the starting city and j is the code of the destination.

## It now wants to compute all pairs of cities connected by one intermediate hope — city i is connected to city j by one intermediate hop if there are direct flights of the form (i,k) and (k,j) for some other city k. The airline is only interested in one hop flights between different cities — pairs of the form (i,i) are not useful.

## Write a Python function onehop(l) that takes as input a list of pairs representing direct flights, as described above, and returns a list of all pairs (i,j), where i != j, such that i and j are connected by one hop. Note that it may already be the case that there is a direct flight from i to j. So long as there is an intermediate k with a flight from i to k and from k to j, the list returned by the function should include (i,j). The input list may be in any order. The pairs in the output list should be in lexicographic (dictionary) order. Each pair should be listed exactly once.

## Here are some examples to show how your function should work.

```bash 
 >>> onehop([(2,3),(1,2)])
[(1, 3)]

>>> onehop([(2,3),(1,2),(3,1),(1,3),(3,2),(2,4),(4,1)])
[(1, 2), (1, 3), (1, 4), (2, 1), (3, 2), (3, 4), (4, 2), (4, 3)]

>>> onehop([(1,2),(3,4),(5,6)])
[]
```

### Solution :

```python
def onehop(l):
    new=[]
    l.sort()
    for i in range(len(l)):
        for j in range(len(l)):
            if l[i]!=l[j]:
                if l[i][1]==l[j][0]:
                    q=l[i][0]
                    w=l[j][1]
                    if q!=w:
                        t=[q,w]
                        t=tuple(t)
                        if t not in new:
                            new.append(tuple(t))
    new.sort()
    return (new)
```

<!-- ## Private Test cases used for evaluation	Input	Expected Output	Actual Output	Status

- Test Case 1	
```bash
contracting([98,21,77,35,11])
 True
True\n
Passed
```

- Test Case 2	
```bash
contracting([-36,25,79,38,11])
 True
True\n
Passed
```

- Test Case 3	
```bash
contracting([100,77,33,11])
 False
False\n
Passed
```

- Test Case 4	
```bash
contracting([12,-11,10,-9,8,-7,6,-5,4,-3,2,-1])
 True
True\n
Passed
```

- Test Case 5	
```bash
contracting([-32,-11,10,-9,8,-7,6,-5,4,-3,2,-1])
 False
False\n
Passed
```

- Test Case 6	
```bash
counthv([23,44,22,1,26,10])
 [2, 1]
[2, 1]\n
Passed
```

15 out of 15 tests passed.
You scored 100.0/100.

## Driver Code :

```python
import ast

def parse(inp):
  inp = ast.literal_eval(inp)
  return (inp)

fncall = input()
lparen = fncall.find("(")
rparen = fncall.rfind(")")
fname = fncall[:lparen]
farg = fncall[lparen+1:rparen]

if fname == "contracting":
  arg = parse(farg)
  print(contracting(arg))

if fname == "counthv":
  arg = parse(farg)
  print(counthv(arg))

if fname == "leftrotate":
  arg = parse(farg)
  savearg = arg
  ans = leftrotate(arg)
  if savearg == arg:
    print(ans)
  else:
    print("Side effect")
``` -->