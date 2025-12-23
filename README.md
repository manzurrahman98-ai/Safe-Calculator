# Safe-Calculator
This is a safe calculator, input is secure cannot breach data
# Install first: pip install simpleeval
from simpleeval import simple_eval
import math

def safe_calculator():
    print("=== Safe Calculator ===")
    print("Available operations: +, -, *, /, **, %, sin(), cos(), tan(), sqrt(), log()")
    print("Type 'q' to quit.\n")

    # Allow math functions inside expressions
    allowed_functions = {
        'sin': math.sin,
        'cos': math.cos,
        'tan': math.tan,
        'sqrt': math.sqrt,
        'log': math.log
    }

    while True:
        expr = input("Enter expression: ").strip()
        if expr.lower() == 'q':
            print("Goodbye!")
            break

        try:
            result = simple_eval(expr, functions=allowed_functions)
            print("Result:", result)
        except Exception as e:
            print("Error:", e)

if __name__ == "__main__":
    safe_calculator()
