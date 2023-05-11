# OpenVINO & OpenCV

## Prepare for OpenVINO Installation
* [Download Python 3.10](https://www.python.org/ftp/python/3.10.9/python-3.10.9-amd64.exe
)

```
CMD> python --version
Python 3.10.9
```

* [Download Git 2.40.1](https://github.com/git-for-windows/git/releases/download/v2.40.1.windows.1/Git-2.40.1-64-bit.exe)
```
CMD> git --version
git version 2.40.1.windows.1
```

## Clone this repo
```
CMD> cd %HOME%
git clone https://github.com/litcoder/ovcv
```

## Clone OpenVINO Notebooks under Virtual Environment
Let's assume you're creating this under your home directory.
```
CMD> cd %HOME%
C:\Users\USER>
```

Create a virtual environment.
```
CMD> python -m venv openvino_env
```

You should see prompt changes after `activating` the virtual environment.
```
CMD> cd openvino_env
CMD> Scripts\activate
(openvino_env) C:\Users\USER\openvino_env>
```

Now clone the `OpenVINO Notebook`.
```
git clone https://github.com/openvinotoolkit/openvino_notebooks.git
```

## Install Dependencies & Laucn
Install dependnet Python modules from `requirements.txt`. This will take some time.
```
python -m pip install --upgrade pip
pip install -r requirements.txt
python -m ipykernel install --user --name openvino_env
```

Launch Jupyter Notebook
```
jupyter lab notebooks
```

## OpenVINO Hands on
### 001-hello-world
* Download & Copy ImageNet Korean Labels</br>
Download [ImageNet Korea Labels](./imagenet/imagenet_2012_ko.txt) which was modified from [todak_todak_python](https://raw.githubusercontent.com/cranberryai/todak_todak_python/master/deep_learning_for_image/ImageNetLabels_ko.txt) then copy it into `openvino_notebooks\notebooks\data\datasets\imagenet\`.


* Open the label</br>
Modify file path to indicate the new label file and pass `encoding="utf-8"` to open() call to avoid `UnicodeDecodeError`.
```python
# Convert the inference result to a class name.
imagenet_classes = open("../imagenet/imagenet_2012_ko.txt", encoding="utf-8").read().splitlines()
```

* Play with your own image

* Quiz: List up 5 next possible items
  * Hint: Numpy [argpartition()](https://numpy.org/doc/stable/reference/generated/numpy.argpartition.html)