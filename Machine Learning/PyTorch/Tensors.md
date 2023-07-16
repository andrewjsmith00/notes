Tensors are the fundamental building blocks of [[Deep Learning]] toolkits like [[PyTorch]]. A tensor is like a multi-dimensional array (more dimentions than a matrix). In deep learning, a tensor is any multi-dimensional array but in mathematics, a tensor is a mapping between vector spaces which can be represented as a multidimensional array.

You can convert a NumPy array to a PyTorch Tensor using the `torch.tensor` method.

## Tensors and Gradients
Tensors have built-in gradient calculation and tracking, so you just need to convert data into tensors and perform computations using the tensor moethods and functions provided by [[Python/ML Frameworks/PyTorch/PyTorch|PyTorch]].

By calling the `tensor.backward` function, PyTorch calculates the derivative of the variable with respect to any variable the computation graph has.