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

Yes, the answer is correct.

Score: 2.5

Feedback:
Elements are moved from the beginning of the list to the end, so the list gets reversed.

Accepted Answers:
(Type: Regex Match)

[ ]*[[ ]*55[ ]*,[ ]*82[ ]*,[ ]*65[ ]*,[ ]*19[ ]*,[ ]*14[ ]*,[ ]*22[ ]*][ ]*


## What is the value of pairs after the following assignment?

```bash
pairs = [ (x,y) for x in range(4,1,-1) for y in range(5,1,-1) if (x+y)%3 == 0 ]
```

### [(4, 5), (4, 2), (3, 3), (2, 4)]

Yes, the answer is correct.

Score: 2.5

Feedback:
All pairs (i,j) with i ∈ {4,3,2}, j ∈ {5,4.3,2} such that i + j is a multiple of 3,

Accepted Answers:
(Type: Regex Match)

[ ]*[[ ]*\([ ]*4[ ]*,[ ]*5[ ]*\)[ ]*,[ ]*\([ ]*4[ ]*,[ ]*2[ ]*\)[ ]*,[ ]*\([ ]*3[ ]*,[ ]*3[ ]*\)[ ]*,[ ]*\([ ]*2[ ]*,[ ]*4[ ]*\)[ ]*][ ]*

## Consider the following dictionary.

```bash
wickets = {"Tests":{"Bumrah":[3,5,2,3],"Shami":[4,4,1,0],"Ashwin":[2,1,7,4]},"ODI":{"Bumrah":[2,0],"Shami":[1,2]}}
```

## Which of the following statements does not generate an error?

 - wickets["ODI"]["Ashwin"][0:] = [4,4]
 - wickets["ODI"]["Ashwin"].extend([4,4])
 - wickets["ODI"]["Ashwin"] = [4,4] (correct)
 - wickets["ODI"]["Ashwin"] = wickets["ODI"]["Ashwin"] + [4,4]
   
Yes, the answer is correct.

Score: 2.5

Feedback:
Direct assignment to a new key adds a value. All other updates result in KeyError.

Accepted Answers:

wickets["ODI"]["Ashwin"] = [4,4]

## Assume that hundreds has been initialized as an empty dictionary:

```bash
hundreds = {}
```

## Which of the following generates an error?

 - hundreds["Tendulkar, international"] = 100
 - hundreds["Tendulkar"] = {"international":100} 
 - hundreds[("Tendulkar","international")] = 100
 - hundreds[["Tendulkar","international"]] = 100 (correct)

Yes, the answer is correct.

Score: 2.5

Feedback:
Dictionary keys must be immutable values.

Accepted Answers:

hundreds[["Tendulkar","international"]] = 100
