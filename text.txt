def calculator():
    while True:
        # Display menu
        print("\nSimple Calculator")
        print("1. Add")
        print("2. Subtract")
        print("3. Multiply")
        print("4. Divide")
        print("5. Exit")

        try:
            # Get user's choice
            choice = int(input("Choose an operation (1-5): "))
            if choice == 5:
                print("Goodbye!")
                break

            # Get two numbers
            num1 = float(input("Enter first number: "))
            num2 = float(input("Enter second number: "))

            # Perform operation
            if choice == 1:
                result = num1 + num2
                print(f"{num1} + {num2} = {result}")
            elif choice == 2:
                result = num1 - num2
                print(f"{num1} - {num2} = {result}")
            elif choice == 3:
                result = num1 * num2
                print(f"{num1} * {num2} = {result}")
            elif choice == 4:
                if num2 == 0:
                    raise ZeroDivisionError("Cannot divide by zero!")
                result = num1 / num2
                print(f"{num1} / {num2} = {result}")
            else:
                print("Invalid choice. Please choose 1-5.")

        except ValueError:
            print("Error: Invalid input. Please enter a numeric value.")
        except ZeroDivisionError as e:
            print(f"Error: {e}")
        except Exception as e:
            print(f"An unexpected error occurred: {e}")
        finally:
            retry = input("Do you want to perform another operation? (yes/no): ")
            if retry.lower() != "yes":
                print("Goodbye!")
                break

# Run the calculator
if __name__ == "__main__":
    calculator()
