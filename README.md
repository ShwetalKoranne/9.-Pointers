# 9.-Pointers

Aim: To study and implement Pointer Operations (Call by value and Call by reference).

Tools Used: VS Code or Programiz online compiler.

# Theory

A pointer in C++ is a variable that stores the memory address of another variable. It allows direct access and manipulation of the data stored at that address.

-->Key Features:
1. Storage of address – A pointer stores the memory location (address) of a variable rather than the value itself.
2. Indirect access – By dereferencing a pointer (using *), you can access or modify the value stored at the address it points to.
3. Flexibility – Pointers enable dynamic memory allocation, array handling, passing large data efficiently, and implementing call by reference.

## Pass by Value
In pass by value, a copy of the actual argument’s value is passed to the function. Changes made inside the function do not affect the original variable.

```

return_type function_name(data_type parameter) {
    // function body
}

int main() {
    data_type variable = value;
    function_name(variable);
}

```

## Pass by Reference
In pass by reference, the function receives the actual variable itself (through an alias). Changes made inside the function affect the original variable.

```

return_type function_name(data_type &parameter) {
    // function body
}

int main() {
    data_type variable = value;
    function_name(variable);
}

```

## Pass by Pointer
In pass by pointer, the function receives the memory address of the variable. By dereferencing the pointer, the function can directly modify the original variable's value.

```

return_type function_name(data_type *parameter) {
    // function body
}

int main() {
    data_type variable = value;
    function_name(&variable);
}

```

# Program-1: Swapping Numbers by Pass by Value

This program demonstrates Pass by Value in C++. Here, the swap function takes copies of variables a and b. Changes made to x and y inside the function affect only these copies, not the original variables. As a result, the swapped values are not reflected in the main function. Pass by value is useful when we do not want the original data to be modified. It is safe but may use more memory for large data types because of copying.

--> Algorithm:
1. Start
2. Declare two integer variables a and b and assign initial values (e.g., 5 and 10).
3. Call the swap function with a and b as arguments.
4. Inside swap, interchange the values of the copies using a temporary variable.
5. Display the values of a and b in main() (observe that they remain unchanged).
6. Stop

# Program-2: Swapping Numbers by Pass by Pointer

In this program, two integer variables a and b are declared and initialized. The swap function is designed to take pointers to integers as parameters. By passing the addresses of a and b, the function can directly modify the original values in memory. Inside swap, the dereference operator * is used to access and interchange the values stored at the given addresses using a temporary variable. Since the actual memory locations are modified, the changes persist even after the function ends. This demonstrates pass by pointer, where arguments are passed as memory addresses.

--> Algorithm:
1. Start
2. Declare two integer variables a and b and initialize them with values.
3. Display the values of a and b before swapping.
4. Call the swap function, passing the addresses of a and b.
5. Inside swap:
  -Store the value pointed to by x in a temporary variable.
  -Assign the value pointed to by y to the location pointed to by x.
  -Assign the value from the temporary variable to the location pointed to by y.
6. Return to main and display the swapped values of a and b.
7. End

# Program-3: Swapping Number by Pass by Reference

This program demonstrates pass by reference in C++. In pass by reference, the function parameters are declared as references using &, meaning they directly refer to the original variables. The swap function exchanges the values of x and y without creating copies, so changes reflect in the calling function. Inside swap, a temporary variable is used to hold one value during the exchange. In main, a and b are swapped by simply passing them to the function, and their values are updated permanently. This method is efficient as it avoids copying and works directly on the original data.

--> Algorithm:
1. Start
2. Declare two integer variables a and b with initial values.
3. Display the values of a and b before swapping.
4. Call the swap function with a and b as arguments.
5. Inside swap function:
  -Store the value of x in a temporary variable temp.
  -Assign the value of y to x.
  -Assign the value of temp to y.
6. Return to main function.
7. Display the swapped values of a and b.
8. End

# Program-4: Salary Incrementation

This C++ program calculates an employee’s salary increment based on specific conditions related to their performance. It takes inputs for salary, research projects, publications, profit, and new projects. If the employee meets at least three combinations of given conditions (projects, profit > 100,000, publications, or new projects), the salary is increased by 20% using pass by reference—which changes the original salary value. If the conditions are not met, a 20% increment is attempted using pass by value, but the original salary remains unchanged because the modification happens on a copy. This demonstrates the difference between pass by reference (affects original data) and pass by value (does not affect original data). Finally, the program displays either the incremented salary or the unchanged salary based on performance.

--> Algorithm:
1. Start
2. Declare variables: proj, pub, prof, new_proj, salary.
3. Take input for salary, proj, pub, prof, and new_proj.
4. If the employee satisfies at least one of the following performance conditions:
  -proj > 0 AND prof > 100000 AND new_proj > 0
  -proj > 0 AND prof > 100000 AND pub > 0
  -proj > 0 AND new_proj > 0 AND pub > 0
  -new_proj > 0 AND prof > 100000 AND pub > 0
→ Call increment_ref(salary) to increase salary by 20%.
5. Else call increment_val(salary) (increment attempted but no change due to pass by value).
6. Display the final salary.
7. End

# Program-5: Changing Array

This program demonstrates pass by reference to modify elements of an array. Two integer arrays arr and arr1 are declared and initialized, but only arr is used. The change_val function takes an integer reference x and a value val, then updates x to val. Initially, the program prints all elements of arr. It then calls change_val for each element of arr, setting all of them to 1000. Finally, the updated array is printed, showing that every element has been modified because references allow direct changes to the original data.

--> Algorithm:
1. Start
2. Declare two integer arrays arr[5] and arr1[5] with initial values {1, 2, 3, 4, 5} and {2, 4, 6, 8, 10} respectively.
3. Define a function change_val(int &x, int val) that sets x = val.
4. Display the elements of arr as the Initial Array.
5. For each element in arr from index 0 to 4, call change_val(arr[i], 1000) to change its value to 1000.
6. Display the updated elements of arr as the Changed Array.
7. End

# Conclusion
These five programs demonstrate different parameter passing techniques in C++—Pass by Value, Pass by Pointer, and Pass by Reference—and how they affect variable manipulation inside functions. Pass by Value works on a copy of the variable, so changes do not reflect back in the calling function. Pass by Pointer and Pass by Reference directly modify the original variable, making changes persistent outside the function. Through swapping numbers, incrementing salaries, and modifying arrays, the codes show that Pass by Value is safe but non-persistent, while Pointer and Reference passing are efficient for in-place updates without returning values.












