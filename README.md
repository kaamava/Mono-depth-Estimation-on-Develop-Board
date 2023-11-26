# Mono-depth-Estimation-on-Develop-Board

The Atlas 200 DK Developer Kit (Model: 3000) is a high-performance AI application development board integrated with Ascend processors. It facilitates users in rapid development and validation, making it versatile for applications such as developer solution verification, higher education, and scientific research.

![image](https://github.com/kaamava/Mono-depth-Estimation-on-Develop-Board/assets/106901273/dbcaddc0-a9c6-416c-8bbc-becfe4eb951b)

To operationalize the monocular vision depth estimation project, we deployed it on the Atlas 200DK development board. Through the Atlas 200 DK development board, we conducted depth estimation inference experiments by utilizing local image data as input. The aim was to estimate the depth of the environment in the images and save the resulting detection images to files.

We constructed a model based on U-net with ResNet as the encoder. To adapt it to the hardware, we made some adjustments. To address redundancy issues, we reduced the number of convolutional kernels and applied a divide-and-conquer approach to them. Additionally, to resolve operator incompatibility, we independently created corresponding operators.
> This project implements the U-Net Convolutional Neural Network with a ResNet encoder (pre-trained on imagenet weights) on the NYU-Depth v2 dataset and achieved a soft accuracy of 83% on the test set.

![image](https://github.com/kaamava/Mono-depth-Estimation-on-Develop-Board/assets/106901273/33f39141-21e7-47ca-8ffa-5432fefa03a2)

## Tech used
- TensorFlow 2.0.0
- Python 3.5.6

## Instructions to run
- Using `anaconda`:
  - Run `conda create --name <env_name> --file recog.yml`
  - Run `conda activate <env_name>`
- Using `pip`:
  - Run `pip install -r requirements.txt`
- `cd` to `src`
- Run `python main.py`

## Model

The model used in this experiment is based on U-Net, constructing a deep learning network for monocular visual depth estimation. It incorporates ideas from DenseNet and ResNet, enhancing the model with dilated convolutional neural networks and residual learning modules. Furthermore, adjustments were made to the model in accordance with the deployment requirements on the Atlas 200DK.


The model we trained is in PyTorch, and PyTorch is not compatible with inference on the Atlas 200DK. To meet the deployment requirements on the development board, we chose the model conversion route: PyTorch → ONNX → Caffe → OM. This pathway minimizes the losses introduced during model conversion, aligns well with the design requirements of the development board, and is better suited to the hardware environment.

The multi-step transformation of computer vision models is crucial for realizing hardware applications.

**The details of the model introduction and conversion are presented in the Monocular-Board.pdf.**

## Output
We can perform real-time monocular visual depth detection using the Atlas 200DK development board. This project has been officially approved by Huawei.

![output](https://github.com/kaamava/Mono-depth-Estimation-on-Develop-Board/assets/106901273/8c694b6d-8317-494a-bdfa-05997e062e01)

![image](https://github.com/kaamava/Mono-depth-Estimation-on-Develop-Board/assets/106901273/bebe6fb4-0edd-4def-a438-0aa94a2a6c9f)



