# Conditional Adversarial Networks (CAN)
This is an tensorflow implementation of [pix2pix](https://github.com/phillipi/pix2pix) based on ['image-to-image translation with conditional adversarial networks'](https://arxiv.org/pdf/1611.07004.pdf).

## Requirements
- Nvidia GPU and cuDNN 5.0
- Tensorflow 1.0.0

## Train
- Clone this repository
```
git clone https://github.com/fullfanta/pix2pix-tensorflow.git
```

- Download database
I borrowed download script from [pix2pix](https://github.com/phillipi/pix2pix).
```
$ cd pix2pix-tensorflow
$ sh datasets/download_datasets.sh facades
$ sh datasets/download_datasets.sh edges2handbags
$ sh datasets/download_datasets.sh edges2shoes
$ sh datasets/download_datasets.sh maps
```

- Train
Train CAN with specific dataset.
```
$ python train.py --dataset=facades --which_direction=BtoA --batch_size=1 --device=gpu
```
I attatch two shell script to train facades(train_facades.sh) and edges2handbags(train_edges2handbags.sh).

- Tensorboard
To see training procedure, you can start tensorboard.
```
$ tensorboard --logdir=result_facades
```

- Examples
![My image](screenshot/screenshot_01.png?raw=true)

By modifying this code, I transformed facial expression from **neutral** to **smile**.
![My image](screenshot/facial_expression_transform_result.png?raw=true)