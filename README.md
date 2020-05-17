# 2D-character generation
## Dataset

17633 face images are used for training.
They are gathered from Twitter.

To crop face region, I used an SSD model, which I had previously trained: https://github.com/y60/ml_practice/blob/master/chainer/ssd/demo.ipynb

## StyleGAN
This repository is based on the official implementation. https://github.com/NVlabs/stylegan2
![sample](https://github.com/y60/stylegan2/blob/master/results/00081-generate-images_~5:0.5/example.png?raw=true)
|     |     |
| ---- | ---- |
|GPU | Quadro RTX 8000 * 1|
|Data | 17633 face images (256*256)|
|StyleGAN config | config-f|
|Command |  `python run_training.py --num-gpus=1 --data-dir=<data-dir> --mirror-augment=true --config=config-f --dataset=<dataset>` |
|Time | 16 days|

### Random results
Trained for 8 days:
![8days](https://github.com/y60/stylegan2/blob/master/results/00012-stylegan2-face_256_-1gpu-config-f/fakes004757_8days_8_5.png?raw=true)

16 days:
![16days](https://github.com/y60/stylegan2/blob/master/results/00012-stylegan2-face_256_-1gpu-config-f/fakes009515_16days_8_5.png?raw=true)
It seems that this training setting has some difficulty in learning plausible structure. It can be avoided by the truncation (next section), or may be suppressed by adjusting training hyper-parameters or aligning the dataset images.

### Truncation experiments

Truncation parameter `0.5` for all layers:

Though shapes are improved, details are too neutralized. (color, painting style,... etc.)
![all0.5](https://github.com/y60/stylegan2/blob/master/results/00080-generate-images_all:0.5/grid.png?raw=true)

Truncation parameter `0.5` only for the first 5 layers (`1.0` for the rest):

Good detail variation is observed. 
![~5:0.5](https://github.com/y60/stylegan2/blob/master/results/00081-generate-images_~5:0.5/grid.png?raw=true)
### Interpolation
### Discussion
### Image2StyleGAN(++)
## StyleALAE
|     |     |
| ---- | ---- |
|GPU | Quadro RTX 8000 * 1|
|Data | 17008 face images (256*256)|
|Command |  `python train_alae.py -c configs/2d-chara.yaml` |
|Time | ? days|
## HoloGAN
## FQ-StyleGAN
