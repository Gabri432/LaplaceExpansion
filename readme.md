# Laplace-Theorem
A simple program in go that will be able to calculate the matrix determinant by using the Laplace Theorem.
You can check the details on `https://en.wikipedia.org/wiki/Laplace_expansion`.

## Features
- It will calculate square matrices of any size.

## Project Structure
- `Laplace Theorem` (main folder), where the following files are located:
  - `laplace.go`, where you find the main functions of the library,
  - `laplace_test.go`, containing all test functions of the library,
  - `types.go`, containing all the custom types used,
  - `readme.md` and `license`.


## How to use it
### Clone the project
```
git clone https://github.com/Gabri432/LaplaceExpansion.git
```
### Run the tests
```
go test [-v] [-run TestFunctionName]
```
### Run the code
```
\...\laplace-theorem> go run .
```

### Example
- Example 1: Creating a new Matrix from code
```
package main

import (
	"fmt"
	laplace "github.com/Gabri432/LaplaceExpansion"
)

func main() {

	row1 := laplace.NewRow([]float64{1, 2, 3, 6})
	row2 := laplace.NewRow([]float64{5, 7, 3, 0})
	row3 := laplace.NewRow([]float64{1, 11, 1, 4})
	row4 := laplace.NewRow([]float64{9, 2, 8, 4})
	matrix := laplace.NewMatrix([]laplace.MatRow{row1, row2, row3, row4})
	fmt.Println(matrix.LaplaceDet())

}

=== Output ===

 120
```

- Example 2: Creating a new Matrix using "MatrixFromTerminal()" function
```

func main() {
  matrix := lapalce.MatrixFromTerminal()
  matrix.Start()
}

=== Output ===

Insert Input:  <<< It will appear a description about how to use the code.
 1) each line creates a row of the Matrix.
 2) each number of the line must be separated by a semicolon;      
 3) once you have finished write END to start running the program.
Example:
 3;2
 1;5
 END    <<< End of description
1;3;3;1 <<< User starts inserting here.
4;2;9;1
5;3;1;7
9;5;6;8
END   <<< User writes 'END' to start calculating the matrix determinant.

Result: -224      <<< Output of the calculation.
```
- Example 3: Inserting wrong input using "MatrixFromTerminal()" and "(Matrix).Start()" functions
```
1;3;3;1
4;2;9
5;3;1;7
9;5;6;8
END                       <<< User writes 'END' to start calculating the matrix determinant.
This isn't a square matrix    <<< Message of error from the code.
 Retry.
```

## Notes

- The project should work properly. However you can test by using the following website:
```
https://matrixcalc.org/det.html
```
- The 'Laplace Expansion' is not much efficient for bigger matrices. Infact it has a time complexity of O(n!).
- Because of that, the code may run slow according to the size of the matrix.
