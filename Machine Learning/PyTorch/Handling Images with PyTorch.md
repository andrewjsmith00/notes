[[Software Development/Python/ML Frameworks/PyTorch/PyTorch|PyTorch]] is able to use images as inputs. When dealing with classification, you place your channels (ie `train` and `test` ) in individual folders and then each class is saved under a folder.

ie. `train/dog/1.jpg`


You can then use the `ImageFolder` to load the images as a [[PyTorch Dataset]].


You can apply [[PyTorch Transforms]] to load the data with transformations such as converting to [[Tensors]] and resizing images.

```python
from torchvision.datasets import ImageFolder
from torchvision import transforms

# Compose transformations
train_transforms = transforms.Compose([
	transforms.ToTensor(),
	transforms.Resize([128,128]),
])

  
# Create Dataset using ImageFolder
dataset_train = ImageFolder(
	"clouds_train",
	transform=train_transforms,
)
```