# Python Notes

## Day 1 + 2

* Definitions
    ```
    * Case-sensitive + indentation important.

    * Algorithm--> step by step instructions to solve any problem.

    * Programming --> is a way of writing these instructions in a language that the computer understands.

    * Syntax --> Grammatical rules for that particular programming language.

* Errors
    ```python
    | Error                     | Meaning                         | Example                  | Reason                 |
    |---------------------------|---------------------------------|--------------------------|------------------------|
    | `SyntaxError` ⭐          | Invalid Python syntax           | `if True print("Hi")`    | Code rule mistake      |
    | `NameError` ⭐            | Variable not found              | `print(age)`             | Variable not defined   |
    | `TypeError` ⭐            | Wrong datatype operation        | `"Age" + 25`             | str + int mismatch     |
    | `ValueError` ⭐           | Correct type, wrong value       | `int("abc")`             | Invalid conversion     |
    | `IndexError`              | Invalid index access            | `[1,2,3][5]`             | Index doesn't exist    |
    | `KeyError`                | Dictionary key missing          | `dict["age"]`            | Key doesn't exist      |
    | `ZeroDivisionError`       | Divide by zero                  | `10 / 0`                 | Division impossible    |
    | `AttributeError`          | Missing method/attribute        | `10.append(5)`           | Object doesn't support |
    | `ImportError`             | Import failure                  | `from x import y`        | Import issue           |
    | `ModuleNotFoundError`     | Module unavailable              | `import xyz`             | Package not installed  |
    | `FileNotFoundError`       | File missing                    | `open("a.txt")`          | File doesn't exist     |
    | `IndentationError`        | Wrong spacing                   | Bad indentation          | Block alignment error  |
    ```
* print() - output ko screen (console/terminal) par display karta hai.
    ```python
    print(*objects, sep=' ', end='\n', file=None, flush=False)


    # Parameters:

    # objects → values/data to print
    # sep     → separator between multiple values
    # end     → what to add after print statement
    # file    → where output is sent
    #           default → sys.stdout (console/screen)
    # flush   → instantly clear output buffer

    # Python automatically converts objects into string format before displaying output.
    ```
* Same line printing

    ```python
    print("A" , "B" , "C")

    Output - A B C
    ```
* Different line printing

    ```python
    print(5 + 3)
    print("B")
    print("5 + 3")

    Output-
    8
    B
    5 + 3
    ```
* f-strings
    ```python
    # f-string ka use variables aur expressions ko easily string ke andar insert karne ke liye hota hai.

    | Formatting      | Meaning                  | Example                 | Output        |
    |-----------------|--------------------------|-------------------------|---------------|
    | `{var}`         | Variable insert          | `f"{name}"`             | `Alex`        |
    | `{a+b}`         | Expression execute       | `f"{10+20}"`            | `30`          |
    | `{num:.2f}` ⭐  | 2 decimal places         | `f"{3.14159:.2f}"`      | `3.14`        |
    | `{num:.3f}`     | 3 decimal places         | `f"{3.14159:.3f}"`      | `3.142`       |
    | `{num:.0f}`     | No decimal (round)       | `f"{9.8:.0f}"`          | `10`          |
    | `{num:,}` ⭐    | Add comma separator      | `f"{1000000:,}"`        | `1,000,000`   |
    | `{num:.2%}` ⭐  | Convert percentage       | `f"{0.9567:.2%}"`       | `95.67%`      |
    | `{text:<10}`    | Left align               | `f"{'AI':<10}"`         | `AI        `  |
    | `{text:>10}`    | Right align              | `f"{'AI':>10}"`         | `        AI`  |
    | `{text:^10}`    | Center align             | `f"{'AI':^10}"`         | `    AI    `  |
    | `{num:+}`       | Show + / - sign          | `f"{10:+}"`             | `+10`         |
    | `{num:05}`      | Zero padding             | `f"{25:05}"`            | `00025`       |
    | `{x=}` ⭐       | Debug variable           | `f"{loss=}"`            | `loss=0.5`    |

    ```
* Comments

    ```python
    # This is a single line python comment.
    # No compiler error.
    # ctrl + /
    # used for multi-line comments also.
    # """ """  → documentation/docstring
    ```
* Variables
    ```
    * case-sensitive.
    * Containers to store data.(Latest values)
    * A-Z, a-z, 0-9(Not start), _ 
    * No other special characters/spaces allowed.
    * camelCase
    * snake_case
    * Values can be modified or swapped.
    * Needn't to be declared with datatype.
    ```
* Data types
    ```python
    * int --> 2
    * float --> 2.0
    * str --> "2"
    * bool --> True/False  # Capital letter T , F
    ```
* Check datatype
    ```python
    type(variable) --> bool
    type(value) --> str
    # it is valid in google notebook
    # but we have to use it with print in our IDE

    print(type(varibale/value)) --> <class 'bool'>
    ```
* Taking input from user
    ```python
    variable = input("prompt")

    # input mein sab kuch = str datatype, so you have to explicitely change the datatype.
    ```
* String concatenation
    ```python
    str + str
    String + Integer ❌  # typeerror
    ```
* Explicit typecasting
    ```python
    age = input()

    Input = 20

    print(age) # 20 but type = str
    print(int(age)) # 20 but type int

    or

    new_age = int(age) # store it in a new variable

    or

    age = int(input()) # starting mein hi krlo
    ```
 ## Day 3 + 4

 * Arithmatic Operators
    ```python
    +   -   /   //  *   **

    * print(5+2.0)
      print(5-2.0)
      print(5*2.0)
      print(5/2) # float dega
      print(5/2.0)
      print(5%2) # remainder
      print(5%2.0)
      print(5//2) # floor division
      print(5**3) # power

      output-
        7.0
        3.0
        10.0
        2.5
        2.5
        1
        1.0
        2
        125

        # floor means- Move towards smaller number (−∞)

        3.5 = 3
        3.0 = 3
        -3.5 = -4

    ```
* Modulo operator = 
    ```python
    * a % b = a - (a // b) * b

    * Modulo result sign = Divisor (second number) sign

    | Case                  | Expression | Calculation                         | Output |
    |-----------------------|------------|-------------------------------------|--------|
    | Positive % Positive   | `10 % 3`   | `10 - (10 // 3) × 3 = 10 - 9`       | `1`    |
    | Exact Division        | `10 % 5`   | `10 - (10 // 5) × 5 = 10 - 10`      | `0`    |
    | Negative % Positive   | `-10 % 3`  | `-10 - (-10 // 3) × 3 = -10 + 12`   | `2`    |
    | Positive % Negative   | `10 % -3`  | `10 - (10 // -3) × -3 = 10 - 12`    | `-2`   |
    | Negative % Negative   | `-10 % -3` | `-10 - (-10 // -3) × -3 = -10 + 9`  | `-1`   |

    Modulo use case

    | Use Case                 | Example Code            | Meaning                         | Output |
    |--------------------------|-------------------------|---------------------------------|--------|
    | Even Number Check ⭐     | `10 % 2 == 0`           | Number divisible by 2           | `True` |
    | Odd Number Check ⭐      | `7 % 2 != 0`            | Remainder exists                | `True` |
    | Divisibility Check ⭐    | `15 % 5 == 0`           | Completely divisible            | `True` |
    | Get Remainder            | `17 % 5`                | Find leftover value             | `2`    |
    | Last Digit of Number ⭐  | `123 % 10`              | Extract last digit              | `3`    |
    | Cycle / Rotation ⭐      | `index % size`          | Repeat values in range          | `0..size-1` |
    | Clock Calculation        | `(10 + 5) % 12`         | Wrap around after limit         | `3`    |
    | Alternate Pattern        | `i % 2`                 | Switch between 0 and 1          | `0/1`  |
    ```
* Assignment operators

    ```python
    * Assignment operators are used to assign values to variables.

    | Operator | Name                     | Example    | Same As       | Result |
    |----------|--------------------------|------------|---------------|--------|
    | `=`      | Assignment               | `x = 10`   | Store value   | `10`   |
    | `+=` ⭐  | Add and assign           | `x += 5`   | `x = x + 5`   | `15`   |
    | `-=` ⭐  | Subtract and assign      | `x -= 5`   | `x = x - 5`   | `5`    |
    | `*=` ⭐  | Multiply and assign      | `x *= 5`   | `x = x * 5`   | `50`   |
    | `/=` ⭐  | Divide and assign        | `x /= 5`   | `x = x / 5`   | `2.0`  |
    | `//=`    | Floor divide and assign  | `x //= 3`  | `x = x // 3`  | `3`    |
    | `%=` ⭐  | Modulo and assign        | `x %= 3`   | `x = x % 3`   | `1`    |
    | `**=`    | Power and assign         | `x **= 2`  | `x = x ** 2`  | `100`  |
    ```
* Comparison operators

    ```python
    * Comparison operators compare two values and return a Boolean result (`True` or `False`).

    | Operator | Name                         | Example       | Meaning                  | Output  |
    |----------|------------------------------|---------------|--------------------------|---------|
    | `==` ⭐  | Equal to                     | `10 == 10`    | Both values same         | `True`  |
    | `!=` ⭐  | Not equal to                 | `10 != 5`     | Values different         | `True`  |
    | `>` ⭐   | Greater than                 | `10 > 5`      | Left bigger than right   | `True`  |
    | `<` ⭐   | Less than                    | `5 < 10`      | Left smaller than right  | `True`  |
    | `>=`      | Greater than or equal to     | `10 >= 10`    | Bigger or equal          | `True`  |
    | `<=`      | Less than or equal to        | `5 <= 10`     | Smaller or equal         | `True`  |

    ```
* bool
    ```python
    | Data Type | Value              | bool() Result |
    |-----------|--------------------|---------------|
    | `int`     | `0`                | `False`       |
    | `int`     | `10`, `-5`         | `True`        |
    | `float`   | `0.0`              | `False`       |
    | `float`   | `3.14`, `-2.5`     | `True`        |
    | `string`  | `""` (empty)       | `False`       |
    | `string`  | `"Hello"`          | `True`        |
    | `list`    | `[]`               | `False`       |
    | `list`    | `[1,2,3]`          | `True`        |
    | `tuple`   | `()`               | `False`       |
    | `tuple`   | `(1,2)`            | `True`        |
    | `dict`    | `{}`               | `False`       |
    | `dict`    | `{"a":1}`          | `True`        |
    | `set`     | `set()`            | `False`       |
    | `set`     | `{1,2}`            | `True`        |
    | `None`    | `None`             | `False`       |
    | `bool`    | `True`             | `True`        |
    | `bool`    | `False`            | `False`       |
    ```
* Logical operators
    ```python
    * Logical operators are used to combine conditional statements and return Boolean results.

    * Multiple conditions ko combine/check karne ke liye use hote hain.

    | Operator | Meaning                    | Example              | Output  |
    |----------|----------------------------|----------------------|---------|
    | `and` ⭐ | Both conditions True       | `True and True`      | `True`  |
    | `or` ⭐  | At least one True          | `True or False`      | `True`  |
    | `not` ⭐ | Reverse Boolean value      | `not True`           | `False` |
    ```
* Memborship operator
    ```python
    Membership operators test whether a value exists in a sequence or collection and return a Boolean result (`True` or `False`).

    | Operator   | Meaning              | Example              | Output |
    |------------|----------------------|----------------------|--------|
    | `in` ⭐     | Value exists         | `2 in [1,2,3]`       | `True` |
    | `not in` ⭐ | Value doesn't exist  | `5 not in [1,2,3]`   | `True` |

    | Data Type | Example             | Output  |
    |-----------|---------------------|---------|
    | String    | `"a" in "cat"`      | `True`  |
    | List      | `5 in [1,5,9]`      | `True`  |
    | Tuple     | `4 in (1,2,3)`      | `False` |
    | Set       | `2 in {1,2,3}`      | `True`  |
    | Dict Key  | `"x" in {"x":10}`   | `True`  |
    ```
* 