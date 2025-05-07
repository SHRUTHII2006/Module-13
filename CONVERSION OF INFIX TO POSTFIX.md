# Exp.No:32  
## CONVERSION OF INFIX TO POSTFIX

---

### AIM  
To Write a Python program to convert given Infix expression to Postfix expression by following the precedence and associative rule. 
The input expression contains only  subtraction and multiplication. Use dictionary to set the priority for operators. Use set to hold the operators used in the given expression.

---

### ALGORITHM

1.Initialize an empty stack for operators.

2.Initialize an empty list for the output (postfix expression).

3.Define a dictionary to set operator precedence: {'-': 1, '*': 2}.

4.Initialize an empty set to store operators used in the expression.

5.For each character in the infix expression:

6.If it's an operand (e.g., a letter or digit), append it to the output list.

      If it's a left parenthesis '(', push it onto the stack.

      If it's a right parenthesis ')':

      Pop operators from the stack and append them to the output list until a left parenthesis '(' is encountered.

      Pop and discard the left parenthesis '('.

      If it's an operator ('-' or '*'):

7.While the stack is not empty, and the top of the stack is not '(', and the precedence of the current operator is less than or equal to the precedence of the operator at the top of the stack:

8.Pop the operator from the stack and append it to the output list.

9.Push the current operator onto the stack.

10.Add the operator to the set of used operators.

11.After processing the entire expression, pop any remaining operators from the stack and append them to the output list.

12.The output list now contains the postfix expression.

### PROGRAM

```
Operators = set([ '-', '*','(',')'])  # collection of Operators

Priority = {'-':1, '*':2} # dictionary having priorities of Operators
 
 
def infixToPostfix(expression): 

    stack = [] # initialization of empty stack

    output = '' 

    

    for character in expression:

        if character not in Operators:  # if an operand append in postfix expression

            output+= character

        elif character=='(':  # else Operators push onto stack

            stack.append('(')

        elif character==')':

            while stack and stack[-1]!= '(':

                output+=stack.pop()

            stack.pop()

        else: 

            while stack and stack[-1]!='(' and Priority[character]<=Priority[stack[-1]]:

                output+=stack.pop()

            stack.append(character)

    while stack:

        output+=stack.pop()

    return output


expression = input()

print('infix notation: ',expression)

print('postfix notation: ',infixToPostfix(expression))
```

### OUTPUT

![image](https://github.com/user-attachments/assets/2f8de42f-4527-4f28-8a3f-3c51503c2e7a)




### RESULT
 Thus the Python program to convert given Infix expression to Postfix expression by following the precedence and associative rule. 
The input expression contains only  subtraction and multiplication. Use dictionary to set the priority for operators. Use set to hold the operators used in the given expression was successfully executed.

