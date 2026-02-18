# DT-Calculator

exp = input("Enter your calculation: ")

numbers = []
operators = []
num = ""

for x in exp:
    if x.isdigit():
        num += x
    else:
        numbers.append(float(num))
        operators.append(x)
        num = ""
numbers.append(float(num))

bodmas = ['^', '/', '*', '+', '-']

for op in bodmas:
    i = 0
    while i < len(operators):
        if operators[i] == op:
            if op == '+':
                result = numbers[i] + numbers[i+1]
            elif op == '-':
                result = numbers[i] - numbers[i+1]
            elif op == '*':
                result = numbers[i] * numbers[i+1]
            elif op == '/':
                result = numbers[i] / numbers[i+1]
            elif op == '^':
                result = numbers[i] ** numbers[i+1]

            numbers[i] = result
            numbers.pop(i+1)
            operators.pop(i)
        else:
            i += 1

print("Result is:", numbers[0])
