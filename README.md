# PyTorch Implementation of MobileNet V3
Reproduction of MobileNet V3 architecture as described in [Searching for MobileNetV3](https://arxiv.org/abs/1905.02244) by Andrew Howard, Mark Sandler, Grace Chu, Liang-Chieh Chen, Bo Chen, Mingxing Tan, Weijun Wang, Yukun Zhu, Ruoming Pang, Vijay Vasudevan, Quoc V. Le, Hartwig Adam on ILSVRC2012 benchmark with [PyTorch](pytorch.org) framework.

# Requirements
## Dataset
Download the ImageNet dataset and move validation images to labeled subfolders.
To do this, you can use the following script: https://raw.githubusercontent.com/soumith/imagenetloader.torch/master/valprep.sh

# Models
| Architecture      | # Parameters | MFLOPs | Top-1 / Top-5 Accuracy (%) |
| ----------------- | ------------ | ------ | -------------------------- |
| [MobileNetV3-Large 1.0](https://github.com/d-li14/mobilenetv3.pytorch/blob/master/pretrained/mobilenetv3-large-b4e262ea.pth) | 5.481M | 216.60 | 74.256 / 91.918 |
| [MobileNetV3-Large 0.75]() | 3.913M | 140.58 |  |
| [MobileNetV3-Small 1.0](https://github.com/d-li14/mobilenetv3.pytorch/blob/master/pretrained/mobilenetv3-small-547c1152.pth) | 2.537M |  56.51 | 67.220 / 87.260 |
| [MobileNetV3-Small 0.75]() | 2.009M |  39.48 |  |


```python
from mobilenetv3 import mobilenetv3_large, mobilenetv3_small

net_large = mobilenetv3_large()
net_small = mobilenetv3_small()

net_large.load_state_dict(torch.load('pretrained/mobilenetv3-large-b4e262ea.pth'))
net_small.load_state_dict(torch.load('pretrained/mobilenetv3-small-547c1152.pth'))
```

# Citation
```
@InProceedings{Howard_2019_ICCV,
author = {Howard, Andrew and Sandler, Mark and Chu, Grace and Chen, Liang-Chieh and Chen, Bo and Tan, Mingxing and Wang, Weijun and Zhu, Yukun and Pang, Ruoming and Vasudevan, Vijay and Le, Quoc V. and Adam, Hartwig},
title = {Searching for MobileNetV3},
booktitle = {The IEEE International Conference on Computer Vision (ICCV)},
month = {October},
year = {2019}
}
```
