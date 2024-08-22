# Week 4 Quiz

## All questions carry equal weightage. All Python code is assumed to be executed using Python3. You may submit as many times as you like within the deadline. Your final submission will be graded.

# Note:

- If the question asks about a value of type string, remember to enclose your answer in single or double quotes.
- If the question asks about a value of type list, remember to enclose your answer in square brackets and use commas to separate list items.

## Consider the following lines of Python function.

```bash
def mystery(l):
    if l == []:
        return(l)
    else:
        return(mystery(l[1:])+l[:1])
```

## What does mystery([22,14,19,65,82,55]) return?


### [55, 82, 65, 19, 14, 22]

<!-- Feedback:
At statement 7, w[1] is the string "mimsy", which cannot be updated in place.

Accepted Answers:
(Type: Numeric) 7 -->

## What is the value of pairs after the following assignment?

```bash
pairs = [ (x,y) for x in range(4,1,-1) for y in range(5,1,-1) if (x+y)%3 == 0 ]
```

### [(4, 5), (4, 2), (3, 3), (2, 4)]

<!-- Feedback:
a[0] == 65, b[3] == 73, c[3] == 73, d[1] == 95
b and c refer to the same list, while a and d are two independent slices. The update to d[1] does not affect any other list. The update to b[2] does not affect a or d. The update to c[3] is also reflected in b[3].

Accepted Answers:
a[0] == 65, b[3] == 73, c[3] == 73, d[1] == 95 -->

## Consider the following dictionary.

```bash
wickets = {"Tests":{"Bumrah":[3,5,2,3],"Shami":[4,4,1,0],"Ashwin":[2,1,7,4]},"ODI":{"Bumrah":[2,0],"Shami":[1,2]}}
```

## Which of the following statements does not generate an error?

 - wickets["ODI"]["Ashwin"][0:] = [4,4]
 - wickets["ODI"]["Ashwin"].extend([4,4])
 - wickets["ODI"]["Ashwin"] = [4,4] (correct)
 - wickets["ODI"]["Ashwin"] = wickets["ODI"]["Ashwin"] + [4,4]

<!-- Feedback:
At statement 7, w[1] is the string "mimsy", which cannot be updated in place.

Accepted Answers:
(Type: Numeric) 7 -->

## Assume that hundreds has been initialized as an empty dictionary:

```bash
hundreds = {}
```

## Which of the following generates an error?

 - hundreds["Tendulkar, international"] = 100
 - hundreds["Tendulkar"] = {"international":100} (correct)
 - hundreds[("Tendulkar","international")] = 100
 - hundreds[["Tendulkar","international"]] = 100

<!-- Feedback:
At statement 7, w[1] is the string "mimsy", which cannot be updated in place.

Accepted Answers:
(Type: Numeric) 7 -->