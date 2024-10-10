\0: Null character, used to signify the end of a string.
\n: Newline character, used to move the cursor to the next line.

TypeError: unsupported operand type(s) for +: 'int' and 'str'

magic commands: %clear & %reset
%clear clears the terminal screen of the notebook, removing any output displayed so far. 
       It doesn't affect the variables or the code.
%reset removes all variables and imports from the current namespace, essentially resetting the environment.
       This doesn't clear the outputs shown in the notebook but clears all in-memory variables.

s.count(5) // TypeError: must be str, not int i.e., s.count('5')

%s and %d are formatting placeholders
print("%s is a great school in %s!"%(name, country))

f-string (formatted string): print(f"My name is {name} and I am {age} years old.") or print(F"...") 
Note :  In Python, both '' (single quotes) and "" (double quotes) are functionally the same.

Indexing returns a single item, but slicing returns a subsequence of items [substring, list, etc].
Python strings are "immutable" which means they cannot be changed after they are created.
s[0]="w" # TypeError: 'str' object does not support item assignment.

Negative indexing in Python strings counts from the end. s[-1] is the last character, s[-2] is the second-to-last, and so on.

1. start -> (+)ve, stop -> (+)ve & step -> (+)ve
    When the step is positive, the slice starts at the start index and goes up to (but not including) the stop index, moving forward through the sequence.
2. start -> (+)ve, stop -> (+)ve & step -> (-)ve
    When the step is negative, the slicing moves backward through the sequence. The start must be greater than the stop, otherwise, the result will be an empty sequence.
3. start -> (-)ve, stop -> (-)ve & step -> (+)ve
    Indexing from last(like -1, -2, ,...) & forward step
4. start -> (-)ve, stop -> (-)ve & step -> (-)ve
    Indexing from last(like -1, -2, ,...) & backward step

The print() function also returns 'None' after printing.

zip function : zip aggregates elements from two iterables (e.g., lists, tuples, strings, etc.) and 
               makes a iterable (e.g., lists, tuples, strings, etc.) of tuples.
    list1 = [1, 2, 3]
    list2 = ['a', 'b', 'c']
    zipped_list = list(zip(list1, list2)) // list or tuple or set
    print(zipped_list)  # Output: [(1, 'a'), (2, 'b'), (3, 'c')]

// list.extend(iterable)
The list.extend() method in Python is used to add elements from another iterable 
(e.g., list, tuple, string) to the end of an existing list.
    fruits = ['apple', 'banana']
    more_fruits = ['orange', 'grape']
    fruits.extend(more_fruits)
    print(fruits)  # Output: ['apple', 'banana', 'orange', 'grape']    

1. In-place sorting modifies the original list directly, without creating a new copy.
2. Out-of-place sorting creates a new list to store the sorted elements, without modifying the original list.    

// x.sort()
    1. Modifies the original list x in-place by arranging its elements in ascending order.
    2. Return value: None
    3. e.g.,
        numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5]
        numbers.sort()
        print(numbers)  # Output: [1, 1, 2, 3, 4, 5, 5, 6, 9]

// sorted(x)
    1. Creates a new list containing the elements of x sorted in ascending order.
    2. Return value: A new sorted list.
    3. e.g.,
        numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5]
        sorted_numbers = sorted(numbers)
        print(sorted_numbers)  # Output: [1, 1, 2, 3, 4, 5, 5, 6, 9]
        print(numbers)  # Output: [3, 1, 4, 1, 5, 9, 2, 6, 5]

// round() function: Rounds a number to a specified number of decimal places.
    Syntax: round(number, ndigits=None)        
    -: ndigits: The number of decimal places to round to. If None (default), the number is rounded to the nearest integer.
    e.g., 
        print(round(3.74159))  # Output: 4
        print(round(3.14159, 2))  # Output: 3.14
        print(round(-3.14159))  # Output: -3
        print(round(-3.14159, 2))  # Output: -3.14

// abs() function: Returns the absolute value of a number, which is the distance of the number from zero.
    Syntax: abs(number)        

// round(1.5)==2 & round(2.5)==2 bcz it rounds to nearest even integer.

// rlist.sort(key=round,reverse=True)
        reverse=True => sort in descending order
        reverse=False => sort in ascending order (by default)
        key=round => first round(ele) and then sort

-: lexicographic order is same as alphabetical order.
    1. apple
    2. banana
    3. ......

// tuple unpacking : (x, y, z) = (255, 0, 0)
        points = (10,20,30)
        x,y,z = points // tuple unpacking : x = (10), y = (20), z = (30)       

//  u = 7, 14, 21 # A tuple is implicitly created without parentheses.
    Even without parentheses, the comma-separated values are interpreted as a tuple.  


/*
    #Flexible unpacking using *
    numbers = (1,2,4,5,6,9)
    *head, last = numbers
    print(head) // [1, 2, 4, 5, 6]
    print(last) // 9 ['int' type]
    type(head) // list
*/    

-: Flexible Unpacking using the * operator, which allows you to capture multiple elements
   from a sequence (like a tuple) into a list. 

// import copy: The statement 'import copy' in Python imports the copy module, which provides functions for 
                creating shallow and deep copies of objects.
                copy.copy(): Creates a shallow copy of an object.
                e.g.,
                    import copy
                    original_list = [1, 2, [3, 4]]
                    shallow_copy = copy.copy(original_list)

                copy.deepcopy(): Creates a deep copy of an object.   
                e.g., 
                    import copy
                    original_list = [1, 2, [3, 4]]
                    shallow_copy = copy.copy(original_list)

        //  list's built-in copy() method
            e.g.,
                l1 = [1,2,3,4,5]
                l2 = l1.copy() // Shallow Copy            
 

// Deep Copy, Shallow Copy & =
    1. A deep copy creates a completely new object, recursively copying all elements and sub-elements.
       e.g.,
            import copy
            list1 = [1, 2, [3, 4], 5]
            list2 = copy.deepcopy(list1)  # deep copy
            list2[2][0] = 99  # modifies an inner list element
            print(list1)  # Output: [1, 2, [3, 4], 5]
            print(list2)  # Output: [1, 2, [99, 4], 5]
        
    2. A shallow copy creates a new object, but the elements inside the new object still reference the original elements.
       If the original list contains mutable elements (like lists, dictionaries, etc.), changes to those elements will reflect in both the original and copied lists.
       e.g., 
            import copy
            list1 = [1, 2, [3, 4], 5]
            list2 = copy.copy(list1)  # shallow copy
            list2[2][0] = 99  # modifies an inner list element
            print(list1)  # Output: [1, 2, [99, 4], 5]
            print(list2)  # Output: [1, 2, [99, 4], 5]

    3. list2 = list1
            No new object is created. Both list1 and list2 point to the same object in memory, 
            so any modification in one affects the other.
        e.g., 
            list1 = [1, 2, 3, 4, 5]
            list2 = list1  # Both variables refer to the same list object
            list2[0] = 99  # Modify an element
            print(list1)  # Output: [99, 2, 3, 4, 5]
            print(list2)  # Output: [99, 2, 3, 4, 5]


// Tuples are immutable in Python
    -: However, if a tuple contains mutable elements (like lists or dictionaries), those mutable elements can 
       still be changed. The tuple itself remains immutable, but the objects inside the tuple that are mutable can be modified.
       e.g.,
            t = (1, 2, [3, 4])
            t[2][0] = 99  # This is allowed because the list inside the tuple is mutable
            print(t)  # Output: (1, 2, [99, 4])


import math : This statement makes the functions and constants defined in the math module available for use in your code.
    e.g.,
        import math

        # Using math functions
        print(math.sqrt(16))  # Output: 4.0 (square root of 16)
        print(math.factorial(5))  # Output: 120 (factorial of 5)

        # Using math constants
        print(math.pi)  # Output: 3.141592653589793 (value of π)


-: Euler's number and Napier's constant => 'e'

import random : used to include the random module
        After importing, you can access functions like 
        random.randint() -> generate random integers.
        random.sample() -> generate a random sample from a sequence(like a list or tuple).
        random.choice() -> select random elements from a sequence.
        random.shuffle() -> shuffle sequence(like a list or tuple).
        e.g.,
            import random
            # Generate a random integer between 1 and 10
            random_number = random.randint(1, 10) [both included]
            print(random_number)
            # Choose a random element from a list
            items = ['apple', 'banana', 'cherry']
            random_item = random.choice(items)
            print(random_item)
            # Shuffle a list randomly
            numbers = [1, 2, 3, 4, 5]
            random.shuffle(numbers)
            print(numbers)

// `range()`
        range() function is a built-in Python function used to generate a sequence of numbers. 
        It is not part of any module and is available by default in Python.
        Syntax: range(start, stop, step)
        start: The starting value of the sequence (inclusive). [by default 0]
        stop: The end value of the sequence (exclusive).
        step: The difference between each number in the sequence (optional) [by default 1]
        e.g.,
            # Creates a range from 0 to 4
            range(5)  
            # Creates a range from 2 to 5
            range(2, 6)  
            # Creates a range from 0 to 8 with a step of 2
            range(0, 10, 2)
        Note: The range() function is often used in for loops to iterate over a sequence of numbers.    


// The general format for list comprehension in Python is:
    Syntax: [expression for item in iterable if condition]
    Components:-
        expression: The value or operation to include in the new list.
        item: The variable representing each element from the iterable.
        iterable: The sequence (like a list, range, or tuple) to iterate over.
        condition (optional): A filter that determines whether the item should be included in the new list.            
        e.g.,
            # Create a list of squares of numbers from 0 to 4
            squares = [x ** 2 for x in range(5)]
            print(squares)  # Output: [0, 1, 4, 9, 16]

-: In the expression:
       -> list1 = [random.randint(1, 100) for _ in range(10)]
       -> _(underscore) is simply a placeholder and could be replaced with any other variable name, 
          but using _ is a common practice when the variable is not used.      


// Sets:
        In Python, a set is an unordered collection of unique elements.
        Key Properties:
            Unordered: The items do not have a specific order.
            Unique: Duplicate elements are automatically removed.
        Empty Set: my_set = set()
        // methods to remove elements from a set
            my_set = {1,2,3,4,5}
            my_set.remove(2)  # Removes 2 from the set (raises KeyError if 2 is not present)
            my_set.discard(3)  # Removes 3 from the set (does nothing if 3 is not present)

// negative modulo operations.
    Python: Follows divisor's sign.
    C++: Follows dividend's sign.            

// In Python, empty strings ("") are evaluated as False, while non-empty strings (e.g., "hello") are evaluated as True.

-: range(10): Generates numbers from 0 to 9 (efficient, no memory storage).
-: list(range(10)): Stores numbers from 0 to 9 in memory explicitly as a list.
-: Both can be iterated, but `range` is more memory-efficient.

/*
    Docstrings in Python are special strings used to document code.
    Syntax: They are written using triple quotes ("""docstring""" or '''docstring'''), and are placed 
            immediately after the function, class, or module definition.
    help(function_name): to get the docstring        
*/

/*
    `s[start:stop:step]`:
    start: The index to start the slice. If None, the slice starts from the beginning (or end if step is negative).
    stop: The index to end the slice. If None, the slice continues to the end (or start if step is negative).
    step: The step between each index. A negative step means the slice moves backwards.
*/

/*
    In Python, if you use if list:, it checks whether the list is non-empty. Here's how it works:
        If the list is not empty, if list: evaluates to True, and the block of code inside the if statement will execute.
        If the list is empty, if list: evaluates to False, and the block of code inside the if statement will not execute.
*/
            
//  sum() is a built-in function. 
    It calculates the sum of all items in an iterable, such as a list or tuple.

/*
    - Method: `isalpha()`
    - Type: String method
    - Function: Checks if all characters in the string are alphabetic
    - Returns: `True` if all characters are alphabetic and the string is not empty; otherwise, `False`
*/    
    
//  `nan` (not a number) is a placeholder for values that do not represent valid numerical results.
    -> Syntax: value1 = float('nan')
    ->  It's a special floating-point value used to represent undefined or unrepresentable numerical results, 
        such as the result of 0/0 or invalid operations.
    -> `isnan()` - Checks if a value is `nan` : under math module    

//  `lambda`: lambda is a keyword used to define anonymous functions (lambda functions).
    Syntax: `lambda` arguments: expression
    Characteristics:
        No function name (anonymous).
        Single expression (no multiple statements).
    e.g.,
        add = `lambda` a, b: a + b
        print(add(3, 4))  # Output: 7

// `filter(function, iterable)` function
    -> First argument (function): A function that defines the condition to filter the elements.
    -> Second argument (iterable): The iterable that contains the elements to be filtered.
    e.g.,
        numbers = [1, 2, 3, 4, 5, 6]
        even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
        print(even_numbers)  # Output: [2, 4, 6]        
    
//  Dictionaries can't have duplicate keys, if you try to assign a value to an existing key, 
    it will overwrite the previous value.

/*
    -> In Python, a `global` variable is a variable defined outside of all functions, accessible throughout the entire program.
    -> To modify a global variable inside a function, you must use the global keyword. 
    -> Without it, Python treats the variable as local to the function.
    e.g.,
        x = 10  # Global variable

        def modify_x():
            global x # # Declared that we are using the global `x`
            x += 5  # Modifies the global variable 'x'

        modify_x()
        print(x)  # Output: 15

*/

// `import pylab`
    ->  pylab is a module that provides a MATLAB like interface for plotting and numerical operations 
        by importing functions from the modules Numpy and Matplotlib.
    ->  e.g.,
            import pylab

            # Create some data
            x = [1, 2, 3, 4, 5]
            y = [2, 4, 6, 8, 10]

            # Create a plot
            pylab.plot(x, y)

            # Add title and labels
            pylab.title("Simple Plot")
            pylab.xlabel("X axis")
            pylab.ylabel("Y axis")

            # Show the plot
            pylab.show()
    

    Note: pylab is considered somewhat outdated, and it's generally recommended to use `matplotlib.pyplot` and `numpy` 
          directly for better clarity and control.

          e.g.,
                import matplotlib.pyplot as plt
                import numpy as np

                # Create some data
                x = np.array([1, 2, 3, 4, 5])
                y = np.array([2, 4, 6, 8, 10])

                # Create a plot
                plt.plot(x, y)

                # Add title and labels
                plt.title("Simple Plot")
                plt.xlabel("X axis")
                plt.ylabel("Y axis")

                # Show the plot
                plt.show()
    
// pylab.linspace: Generates an array of evenly spaced values between two specified endpoints.
    e.g.,
        import pylab
        # Generate an array of 10 evenly spaced values between 1 and 10
        values = pylab.linspace(1, 10, 15)
        print(values)
    

