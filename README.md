while True:
    # Take user input
    num1 = float(input("Enter first number: "))
    operator = input("Enter operator (+, -, *, /): ")
    num2 = float(input("Enter second number: "))

    # Perform calculation based on operator
    if operator == "+":
        result = num1 + num2
    elif operator == "-":
        result = num1 - num2
    elif operator == "*":
        result = num1 * num2
    elif operator == "/":
        result = num1 / num2
    else:
        print("Invalid operator.")
        continue

    # Display result
    print(f"{num1} {operator} {num2} = {result}")

    # Ask user if they want to perform another calculation
    another_calculation = input("Do you want to perform another calculation? (Y/N) ").upper()
    if another_calculation != "Y":
        break
