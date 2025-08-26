# GPU Assignment 1 – Image Transformation using CUDA

This repository contains my solution for **CS6023: GPU Programming – Assignment 1**.  
The task was to implement **parallel CUDA kernels** to perform two image transformations on RGB matrices.

---

## Transformations

### 1. Inverted Gray Scale

```
gray(i,j) = floor((red(i,j) + green(i,j) + blue(i,j)) / 3)
final(i,j) = gray(n - i, j)
```

### 2. Thomas Transformation
```
res(i,j) = floor(0.5 × red(i,j)) + floor(sqrt(green(i,j))) + blue(i,j)
```

## Input / Output Format
- **Input:**
  - First line: `rows cols`
  - Followed by 3 matrices (Red, Green, Blue channels).
- **Output:**
  - Two matrices (Inverted Grayscale, Thomas Transformation) of the same dimensions.


## Sample Input

```
2   3        Dimension of matrix
1   2   4    Red channel of matrix of dim 2 × 3
12  11  4
2   4   4    Green channel of matrix of dim 2 × 3
2   4   4
6   8   4    Blue channel of matrix of dim 2 × 3
6   8   4
```



## Sample Output


| 6 | 7 | 4 |
|---|---|---|
| 3 | 4 | 4 |

| 7 |11 | 8 |
|---|---|---|
| 13 | 15 | 8 |


- The first matrix is the **Inverted Grayscale** result.  
- The second matrix is the **Thomas Transformation** result.  

---

## How to Run
1. Place your `transformation.cu` file inside the `submit/` folder.  
2. Compile with:
   ```bash
   nvcc your_idno.cu -o gpu_assignment


Run with provided tester:

`bash test.sh`

