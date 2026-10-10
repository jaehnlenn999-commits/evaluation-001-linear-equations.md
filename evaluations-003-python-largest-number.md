Evaluation 003 — Python Largest Number

User Question

Write a Python function that returns the largest number in a list.

AI Response

def largest_number(numbers):
    largest = 0

    for number in numbers:
        if number > largest:
            largest = number

    return largest

The AI claimed that the function works for any list of numbers and returns the largest value.

Evaluation

Criterion| Score
Accuracy| 2/5
Relevance| 5/5
Reasoning| 2/5
Instruction Following| 4/5

Problem Identified

The function initializes "largest" to zero. When every number in the list is negative, no number will be greater than zero, so the function incorrectly returns zero, even though zero is not in the list.

Example

Input:

[-8, -3, -12, -5]

Actual output:

0

Expected output:

-3

Corrected Code

def largest_number(numbers):
    if not numbers:
        return None

    largest = numbers[0]

    for number in numbers:
        if number > largest:
            largest = number

    return largest

Overall Assessment

Needs Improvement

Evaluator Reasoning

The response is relevant to the requested task but fails for lists containing only negative numbers. Initializing the largest value to zero introduces an incorrect assumption about the input. Initializing it with the first list element fixes this issue for non-empty lists. The corrected implementation also handles an empty list by returning "None", indicating that no largest number exists.