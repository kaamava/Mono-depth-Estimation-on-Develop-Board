# Mono-depth-Estimation-on-Develop-Board

The Atlas 200 DK Developer Kit (Model: 3000) is a high-performance AI application development board integrated with Ascend processors. It facilitates users in rapid development and validation, making it versatile for applications such as developer solution verification, higher education, and scientific research.

![image](https://github.com/kaamava/Mono-depth-Estimation-on-Develop-Board/assets/106901273/dbcaddc0-a9c6-416c-8bbc-becfe4eb951b)

To operationalize the monocular vision depth estimation project, we deployed it on the Atlas 200DK development board. Through the Atlas 200 DK development board, we conducted depth estimation inference experiments by utilizing local image data as input. The aim was to estimate the depth of the environment in the images and save the resulting detection images to files.

We constructed a model based on U-net with ResNet as the encoder. To adapt it to the hardware, we made some adjustments. To address redundancy issues, we reduced the number of convolutional kernels and applied a divide-and-conquer approach to them. Additionally, to resolve operator incompatibility, we independently created corresponding operators.
> This project implements the U-Net Convolutional Neural Network with a ResNet encoder (pre-trained on imagenet weights) on the NYU-Depth v2 dataset and achieved a soft accuracy of 83% on the test set.

![image](https://github.com/kaamava/Mono-depth-Estimation-on-Develop-Board/assets/106901273/33f39141-21e7-47ca-8ffa-5432fefa03a2)

## Tech used:
- TensorFlow 2.0.0
- Python 3.5.6

## Instructions to run:
- Using `anaconda`:
  - Run `conda create --name <env_name> --file recog.yml`
  - Run `conda activate <env_name>`
- Using `pip`:
  - Run `pip install -r requirements.txt`
- `cd` to `src`
- Run `python main.py`

