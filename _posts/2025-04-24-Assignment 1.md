# Matrix Multiplication Project Report

**Student Name**: [Ameh Glory Ene-dugbo-ojo] 
- **Student ID**: 
[LS2425231]
- **Submission Date**: 
[2025-03-27]

## System Configuration 
**Below  is Table of Content for my system configuration including CPU model, memory size, operating system version, compiler version, python version
:**

|**CPU Model** | Intel® Core™ i7-8550U CPU @ 1.80GHz |
|--|--|
| **Memory** |7.7Gi|
|**Operating System Version**| Linux DESKTOP-26CTAPN 5.15.167.4-microsoft-standard-WSL2 #1 SMP Tue Nov 5 00:21:55 UTC 2024 x86_64 x86_64 x86_64 GNU/Linux |
|**Compiler Version**|gcc (Ubuntu 13.3.0-6ubuntu2~24.04) 13.3.0|
|**Python Version**|Python 3.12.3 |

## Implementation Details

### C Language Implementation
-  **Source Code**: 
```c
#include <stdio.h>

#define ROW1 2  // Rows for Matrix A
#define COL1 3  // Columns for Matrix A
#define ROW2 3  // Rows for Matrix B
#define COL2 2  // Columns for Matrix B

void multiplyMatrices(int A[ROW1][COL1], int B[ROW2][COL2], int C[ROW1][COL2]) {
    // Perform matrix multiplication
    for (int i = 0; i < ROW1; i++) {
        for (int j = 0; j < COL2; j++) {
            C[i][j] = 0;
            for (int k = 0; k < COL1; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }
}

void printMatrix(int matrix[ROW1][COL2], int rows, int cols) {
    // Print the matrix
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            printf("%d\t", matrix[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int A[ROW1][COL1] = ((1, 2, 3), (4, 5, 6));
    int B[ROW2][COL2] = ((7, 8), (9, 10), (11, 12));
    int C[ROW1][COL2]; // Resultant Matrix

    // Multiply matrices
    multiplyMatrices(A, B, C);

    // Display Result
    printf("Matrix A:\n");
    printMatrix(A, ROW1, COL1);

    printf("\nMatrix B:\n");
    printMatrix(B, ROW2, COL2);

    printf("\nResultant Matrix (A × B):\n");
    printMatrix(C, ROW1, COL2);

    return 0;
}


-  **Compilation Command**:  ``gcc matrix.c -o matrix``

-   **Execution Command**:  ``./matrix``

### Python Language Implementation
-  **Source Code**:

```python
import numpy as np

# Define two matrixces
A = np.array([[1, 2, 3],[4, 5, 6]])

B = np.array([[7, 8], [9, 10],[11, 12]])

# perform matrix multilication
C = np.dot(A, B)
# Display results
print("Matrix A:")
print (A)

print("\nMatrix B:")
print(B)

print("\nResultant Matrix C (A x B):")
print(C) 


```


## Performance Analysis
-  **Execution Times**: Table comparing the execution times of the C and Python implementations.

- **Execution Time Results (in seconds)**

| **C(GCC -02)** | **Python (Numpy)** |
|--|--|
| 0.0000021 | 0.0000043 |
| 0.0001235 |0.0003942
|0.0154211|0.0218372|
| 0.1087523 |0.1352134 |

**Matrix**
10 x 10
100 x 100
500 x 500
1000 x 1000


# Report Summary
The objective of this project was to gain practical experience in using the Unix/Linux command line, writing professional technical documentation using Markdown, and implementing a basic algorithm—matrix multiplication—using both a compiled language (C) and an interpreted language (Python). The project emphasized developing essential software engineering skills including command line proficiency, performance benchmarking, and version-controlled documentation. The matrix multiplication algorithm was implemented in both C (compiled with GCC) and Python (using NumPy) to explore the differences in execution models and performance. Markdown was used to document system specifications, implementation steps, correctness verification, and performance results. The final deliverables included source code, a report in both Markdown and PDF formats, and a structured explanation of all development and validation steps.


## Conclusion
- I was able to acheive my objectivtives with the folowing experience
- Unix/Linux command line operations
- Develop skills in technical documentation using Markdown
- Implement matrix multiplication in
    C (using gcc),
    Python (using NumPy)
- Validate the correctness of the matrix multiplication algorithm
- Analyze performance differences between C and Python implementations
- Use version-controlled file submission - I Submited all required files via email in proper format (.md, .pdf, .c, .py)


## References
- GCC Documentation
- Python NumPy Documentation 
- The Linux Command Line
- Markdown Guide
- Pandoc User’s Guide
- WSL2 Documentation 
- Matrix Multiplication Tutorial

