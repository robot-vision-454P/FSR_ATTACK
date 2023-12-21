## Model

적대적 공격을 받은 feature인지 구분을 하는 모듈을 추가하였다.

따라서 모든 input이 아니라 공격을 받은 이미지에 대해서 선택적으로 적대적 방어를 하여 원본 이미지에 대한 성능을 향상시켰다.

![MODEL_FIGURE](/figures/figure.png "framework")

## Setup

```
conda env create -n FSRGAN python=3.7
conda activate FSRGAN
conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.3 -c pytorch
conda install tqdm
```

## Train

```
python train.py --save_name cifar10_vgg16 --dataset cifar10 --model vgg16 --device 0 --epoch 200 --bs 256
```

## Test

```
python test.py --load_name cifar10_vgg16 --dataset cifar10 --model vgg16 --device 0
```

## Reference

https://github.com/wkim97/FSR
