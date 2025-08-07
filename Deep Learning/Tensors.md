Tensors are mathematical objects that generalize scalars, vectors, and matrices to higher dimensions. Here's an overview:

## What are Tensors?

A tensor is a multi-dimensional array of numbers that follows specific transformation rules. Think of them as:

- **Rank 0**: Scalar (single number)
- **Rank 1**: Vector (1D array)
- **Rank 2**: Matrix (2D array)
- **Rank 3+**: Higher-dimensional arrays

## Key Properties

**Shape**: The dimensions of a tensor (e.g., a 3×4×5 tensor has shape (3,4,5))

**Rank/Order**: The number of dimensions (a matrix is rank-2, a 3D array is rank-3)

**Data Type**: The type of numbers stored (integers, floats, etc.)

## Common Applications

**Machine Learning**: Tensors are fundamental in deep learning frameworks like TensorFlow and PyTorch for representing:

- Input data (images, text, audio)
- Model weights and biases
- Intermediate computations

**Physics**: Used to describe physical quantities that have directional properties, like:

- Stress and strain in materials
- Electromagnetic fields
- Spacetime in relativity

**Computer Graphics**: For transformations, lighting calculations, and 3D operations

## Tensor Operations

Common operations include:

- **Addition/Subtraction**: Element-wise operations
- **Multiplication**: Various types (element-wise, dot product, matrix multiplication)
- **Reshaping**: Changing dimensions while preserving data
- **Slicing**: Extracting sub-tensors
- **Broadcasting**: Operations between tensors of different shapes

## Programming Libraries

Popular libraries for working with tensors:

- **NumPy**: Basic tensor operations (called arrays)
- **TensorFlow**: Google's ML framework
- **PyTorch**: Facebook's ML framework
- **JAX**: High-performance scientific computing

Note, tensors are not Matrix:
## Think of it This Way

- A **matrix** is like a spreadsheet (2D table)
- A **3D tensor** is like a stack of spreadsheets
- A **4D tensor** is like multiple stacks of spreadsheets
**Matrix** (always 2D):
```
[1, 2, 3]
[4, 5, 6]
```
**3D Tensor**:
```
[[[1, 2], [3, 4]], 
 [[5, 6], [7, 8]]]
```

Tensors are highly used in NN but, here is a very good explanation why they were invented by [[Richard Feynman]] in this [video](https://www.youtube.com/watch?v=k2FP-T6S1x0)
