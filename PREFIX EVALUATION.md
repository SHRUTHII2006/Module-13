# Exp.No:34  
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
OPERATORS=set(['*','-','+','%','/','**'])

def evaluate(expression):

    expression=expression[::-1]

    stack = []

    for char in expression:

        if char not in OPERATORS:

            stack.append(char)

        else:

            a=stack.pop()

            b=stack.pop()

            stack.append(str(eval(a+char+b)))

    return stack[0]
    
test_expression = input()

print(f"Prefix Expression : {test_expression}")

print(f"Evaluation result : {evaluate(test_expression)}")

```


### OUTPUT

![image](https://github.com/user-attachments/assets/8b29d9b1-4144-4a44-863e-e4f2ff5ea093)


### RESULT

Thus the Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction was successfully executed.
