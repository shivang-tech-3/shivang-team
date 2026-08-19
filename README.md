# shivang-team
python calculator
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error: Division by zero is undefined."
    return x / y

def calculator():
    operations = {
        "1": ("Addition", add, "+"),
        "2": ("Subtraction", subtract, "-"),
        "3": ("Multiplication", multiply, "*"),
        "4": ("Division", divide, "/"),
    }

    while True:
        print("\n--- Python Calculator ---")
        for key, (name, _, symbol) in operations.items():
            print(f"{key}. {name} ({symbol})")
        print("5. Exit")

        choice = input("\nSelect an operation (1-5): ").strip()

        if choice == "5":
            print("Goodbye!")
            break

        if choice not in operations:
            print("Invalid choice. Please select an option from 1 to 5.")
            continue

        try:
            num1 = float(input("Enter the first number: "))
            num2 = float(input("Enter the second number: "))
        except ValueError:
            print("Invalid input. Please enter valid numeric values.")
            continue

        name, func, symbol = operations[choice]
        result = func(num1, num2)

        if isinstance(result, str):
            print(result)
        else:
            print(f"\nResult: {num1} {symbol} {num2} = {result}")

if __name__ == "__main__":
    calculator()
