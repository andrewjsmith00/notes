Convolutional Neural Networks are a way of [[Handling Images with PyTorch]]. It passes filters which are the [[Dot Product]] of the input tensor and the filter tensor which is then used to produce an output.

A sample in [[Software Development/Python/ML Frameworks/PyTorch/PyTorch|PyTorch]] looks like:
```python
class Net(nn.Module):
	def __init__(self, num_classes):
		super().__init__()
		# Define feature extractor
		self.feature_extractor = nn.Sequential(
			nn.Conv2d(3, 32, kernel_size=3, padding=1),
			nn.ELU(),
			nn.MaxPool2d(kernel_size=2),
			nn.Conv2d(32, 64, kernel_size=3, padding=1),
			nn.ELU(),
			nn.MaxPool2d(kernel_size=2),
			nn.flatten(),
		)
```