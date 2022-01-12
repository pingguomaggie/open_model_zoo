# online mstcn++

## Use Case and High-Level Description
This is an online action segmentation network for 16 classes trained on Intel dataset. It is an online version of MSTCN++ [1]. The difference between online mstcn++ and mstcn++ is that the former accept stream video as input while the latter assume the whole video is given.
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

The input to the network is feature vectors at each frame, i.e., 1024xL where L is the number of frames(batch size).

### Output

The ouput is [predictions, fea_his] where predictions is the action classification and prediction results. fea_his is the model layer features in past frames

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
