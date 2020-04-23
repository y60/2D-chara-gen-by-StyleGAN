# 2D-character generation by StyleGAN 
This repositry is based on the official implementation. https://github.com/NVlabs/stylegan2

## Dataset

17633 face images are used for training.
They are gathered from Twitter.

To crop face region, I used an SSD model, which I had previously trained: https://github.com/y60/ml_practice/blob/master/chainer/ssd/demo.ipynb

## Training

|     |     |
| ---- | ---- |
|GPU | Quadro RTX 8000 * 1|
|Data | 17633 face images (256*256)|
|config | config-f|
|Command |  `python run_training.py --num-gpus=1 --data-dir=<data-dir> --mirror-augment=true --config=config-f --dataset=<dataset>` |
|time | 16 days|

## Results

### Generation

### Interpolation
