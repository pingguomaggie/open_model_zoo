# online mstcn++

## Use Case and High-Level Description
This is a action segmenation network for 16 classes trained on Intel Dataset of scale balancing experiment.  The network structure is similar to MSTCN++ [1] but modified into online version. It is developed for online action segmenation where the data input is video stream.
[1] Li, Shi-Jie, et al. "Ms-tcn++: Multi-stage temporal convolutional network for action segmentation." IEEE transactions on pattern analysis and machine intelligence (2020).

## ONNX Models

We provide pre-trained models in ONNX format for user convenience.

### Steps to Reproduce PyTorch to ONNX Conversion

Model is provided in ONNX format, which was obtained by the following steps.
TODO

## Model specification

| Metric                          | Value                                     |
|---------------------------------|-------------------------------------------|
| Source framework                | PyTorch\*                                 |

### Accuracy

TODO



| Metric                          | Value                                     |
|---------------------------------|-------------------------------------------|
| GOPs                            | TODO                                   |
| MParams                         | TODO                                      |

### Input

Feature vectors : 1024xL where L is the video length

### Output

action classification results : [predictions, fea_his]
The predictions is the action classification and prediction result with size of [4,1,Nclass*4,L] 
fea_his is a list of history features with length of 4. Each fea_his[i] (i=0,1,2,3) is the history features at the i-th block.

## Download a Model and Convert it into Inference Engine Format

You can download models and if necessary convert them into Inference Engine format using the [Model Downloader and other automation tools](../../../tools/model_tools/README.md) as shown in the examples below.

An example of using the Model Downloader:
```
omz_downloader --name <model_name>
```

An example of using the Model Converter:
```
omz_converter --name <model_name>
```

## Legal Information

The original model is distributed under the following
[license](https://github.com/fatchord/WaveRNN/blob/master/LICENSE.txt)

```
MIT License

Copyright (c) 2019 fatchord (https://github.com/fatchord)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
