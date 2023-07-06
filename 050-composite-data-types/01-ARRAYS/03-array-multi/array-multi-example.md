Sure! Here are two example programs that demonstrate the topics learned in the lesson: one for multidimensional arrays and the other for passing arrays between functions in Go.

Program 1: Multidimensional Arrays

```go
package main

import "fmt"

func main() {
	// Declaring and initializing a two-dimensional array
	var matrix [3][3]int

	// Assigning values to the elements of the two-dimensional array
	matrix[0] = [3]int{1, 2, 3}
	matrix[1] = [3]int{4, 5, 6}
	matrix[2] = [3]int{7, 8, 9}

	// Accessing and displaying elements of the two-dimensional array
	for i := 0; i < len(matrix); i++ {
		for j := 0; j < len(matrix[i]); j++ {
			fmt.Printf("%d ", matrix[i][j])
		}
		fmt.Println()
	}
}
```

Program 2: Passing Arrays Between Functions

```go
package main

import "fmt"

// Function to modify an array by value
func modifyArrayByValue(array [5]int) {
	array[0] = 10
}

// Function to modify an array by pointer
func modifyArrayByPointer(array *[5]int) {
	(*array)[0] = 10
}

func main() {
	// Declaring and initializing an array
	array := [5]int{1, 2, 3, 4, 5}

	fmt.Println("Original array:", array)

	// Passing the array by value to the modifyArrayByValue function
	modifyArrayByValue(array)
	fmt.Println("After modifyArrayByValue:", array)

	// Passing the array by pointer to the modifyArrayByPointer function
	modifyArrayByPointer(&array)
	fmt.Println("After modifyArrayByPointer:", array)
}
```

Explanation:
- Program 1 demonstrates the usage of a two-dimensional array. We declare and initialize a 3x3 matrix, assign values to its elements, and then display the elements using nested for loops.

- Program 2 showcases passing arrays between functions. We define two functions: `modifyArrayByValue` and `modifyArrayByPointer`. The first function receives an array by value, attempts to modify its first element, but the modifications do not affect the original array. The second function receives a pointer to an array, modifies the first element using the pointer, and the changes persist in the original array. The main function initializes an array, passes it to the two functions, and displays the array before and after the function calls to observe the effects.

Note: In Go, arrays are passed by value, meaning a copy of the array is made when passing it to a function. To modify an array and have the changes reflected outside the function, you can pass a pointer to the array instead.

Feel free to run these programs to see the output and experiment with different array values and sizes.