# Variables

All variables in MonkeyPy will be public variables in MonkeyC.

In MonkeyPy, they can be declared anywhere, but anytime a variable is detected by the transpiler, it will be added to the beginning of a chunk of code that automatically allocates the variables properly and efficiently.

Optimization will be prioritized by the transpiler, so anytime a variable is declared in MonkeyPy, it will be placed in the proper spot in the corresponding MonkeyC code.

Just like in Python, variables do not need type declaration. Transpiling will not require any special type checking as MonkeyC also does not require declaring variable type.