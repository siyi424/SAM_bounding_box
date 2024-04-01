# SAM_bounding_box

## Pre-requirement
python>=3.8, pytorch>=1.7, torchvision>=0.8

Installing CUDA on wsl2: 
https://docs.nvidia.com/cuda/wsl-user-guide/index.html

Installing both PyTorch and TorchVision with CUDA support: 
```
pip3 install torch torchvision torchaudio
```
Installing SAM: 
```
pip install git+https://github.com/facebookresearch/segment-anything.git (not successed)

or 

git clone git@github.com:facebookresearch/segment-anything.git
cd segment-anything; pip install -e .
```

Installing other libs:
```
pip install opencv-python pycocotools matplotlib onnxruntime onnx
```

## Issues
Navigate up a directory level to fix bug importing from segment_anything:
Make sure, the local folder name where stored the sources of segment_anything shouldn't be the 'segment_anything', could be 'sam' or others.
https://github.com/facebookresearch/segment-anything/pull/66
```
Currently, if you run this script as specified in README.md, 
line 8 will throw ModuleNotFoundError: No module named 'segment_anything'. 
Currently, the only way to fix this is to either move amg.py up a directory, or add these two lines to it. 
This is because init.py is in segment_anything, i.e. it is only accessible from the main dir. This should also make relative file locations passed into the script be read to/written 
from with respect to the main directory, not scripts/.
```
