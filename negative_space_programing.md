## Negative Space Programming

### Concept

Negative Space Programming is a defensive programming technique that focuses on actively restricting the inputs to a program or function to ensure they adhere to specific constraints or requirements. This approach helps to prevent invalid data from being processed, thereby reducing potential errors and increasing code robustness.

### Example

Consider a function designed to multiply two natural numbers. Instead of writing a simple multiplication function, we incorporate checks to ensure the inputs are valid natural numbers (non-negative integers).

#### Traditional Approach

```python
def mult_natural_numbers(a: int, b: int):
    return a * b
```

#### Negative Space Programming Approach

```python
def mult_natural_numbers(a: int, b: int) -> int:
    # Actively restrict the input of the program to ensure it adheres to specific constraints or requirements
    if not isinstance(a, int) or not isinstance(b, int):
        raise ValueError("Inputs must be of type integers.")
    if a < 0 or b < 0:
        raise ValueError("Inputs must be natural numbers (non-negative integers).")
    
    # Main program logic starts here ------
    result = a * b
    # Main program logic ends here -------
    
    # This ensures the output adheres to the specific constraints or requirements
    if not isinstance(result, int):
        raise ValueError("Output must be of type integer.")
    
    return result
```

### Steps Involved

1. **Input Validation**: Before executing the main logic of the function, validate the inputs to ensure they meet the required criteria.
    - Check if the inputs are of the correct type (e.g., integers).
    - Check if the inputs fall within the expected range (e.g., non-negative for natural numbers).

2. **Main Logic Execution**: Perform the core logic of the function (e.g., multiplication).

3. **Output Validation**: After executing the main logic, validate the output to ensure it meets the required criteria.
    - Check if the output is of the correct type.

### Benefits

- **Error Prevention**: By validating inputs and outputs, potential errors due to invalid data are caught early.
- **Robustness**: The function becomes more robust and reliable as it explicitly handles unexpected input conditions.
- **Maintainability**: Clear input and output constraints make the function easier to understand and maintain.

### Usage

Negative Space Programming is particularly useful in scenarios where:
- The function is exposed to external input (e.g., user input, API calls).
- The function's correctness heavily depends on the validity of its inputs.
- The function is part of a larger system where input validation is crucial to ensure system stability.

### Conclusion

Negative Space Programming is a valuable technique for enhancing code quality by actively restricting inputs and validating outputs. Incorporating this practice into your programming routine can significantly improve the reliability and maintainability of your code.
