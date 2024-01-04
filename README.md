# CIFA-Net
CIFA-Net: Cross-modal Feature Alignment and Information Complementation Network for RGB-D Semantic Segmentation


## Usage
### Installation
1. Requirements

- Python 3.7+
- PyTorch 1.7.0 or higher
- CUDA 10.2 or higher

2. Install all dependencies.
```shell
- torch==1.8.2+cu102
- cudnn==7.6.5
- easydict>=1.9
- opencv-python>=4.5.0
- timm>=0.4.10
- scipy>=1.7.0
- tqdm>=4.40.0
- tensorboardX>=2.2
- numpy~=1.23.5
- torch~=1.8.1
```

### Datasets
Orgnize the dataset folder in the following structure:
```shell
<datasets>
|-- <DatasetName1>
    |-- <RGBFolder>
        |-- <name1>.<ImageFormat>
        |-- <name2>.<ImageFormat>
        ...
    |-- <ModalXFolder>
        |-- <name1>.<ModalXFormat>
        |-- <name2>.<ModalXFormat>
        ...
    |-- <LabelFolder>
        |-- <name1>.<LabelFormat>
        |-- <name2>.<LabelFormat>
        ...
    |-- train.txt
    |-- test.txt
|-- <DatasetName2>
|-- ...
```
`train.txt` contains the names of items in training set, e.g.:
```shell
<name1>
<name2>
...
```

### Train
Run the train by:
```shell
CUDA_VISIBLE_DEVICES="0,1.." python -m torch.distributed.launch --nproc_per_node="n" train.py
 ```

### Evaluation
Run the evaluation by:
```shell
CUDA_VISIBLE_DEVICES="0,1.." python eval.py -d="n" -e="epoch number or range"
```
## Publication
If you find this repo useful, please consider referencing the following paper:
```
@article{
  title={CIFA-Net: Cross-modal Feature Alignment and Information Complementation Network for RGB-D Semantic Segmentation},
  author={Bin Gea, Yiming Lu, Chenxing Xia, Xu Zhu, Mengya Gao, Ningjie Chen, Junming Guan},
}
```

