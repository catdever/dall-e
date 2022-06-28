# min(DALL·E)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kuprel/min-dalle/blob/main/min_dalle.ipynb)

This is a minimal implementation of [DALL·E Mini](https://github.com/borisdayma/dalle-mini).  It has been stripped to the bare essentials necessary for doing inference, and converted to PyTorch.  The only third party dependencies are `torch` for the torch model and `flax` for the flax model.

### Setup

Run `sh setup.sh` to install dependencies and download pretrained models.  In the bash script, GitHub LFS is used to download the VQGan detokenizer and the Weight & Biases python package is used to download the DALL·E Mini and DALL·E Mega transformer models.  These models can also be downloaded manually: 
[VQGan](https://huggingface.co/dalle-mini/vqgan_imagenet_f16_16384), 
[DALL·E Mini](https://wandb.ai/dalle-mini/dalle-mini/artifacts/DalleBart_model/mini-1/v0/files), 
[DALL·E Mega](https://wandb.ai/dalle-mini/dalle-mini/artifacts/DalleBart_model/mega-1-fp16/v14/files)

### Usage

Use the command line python script `image_from_text.py` to generate images. Here are some examples:

```
python image_from_text.py --seed=7 --text='alien life'
```
![Alien](examples/alien.png)


```
python image_from_text.py --mega --seed=4 --text='a comfy chair that looks like an avocado'
```
![Avocado Armchair](examples/avocado_armchair.png)


```
python image_from_text.py --mega --seed=100 --text='court sketch of godzilla on trial'
```

![Godzilla Trial](examples/godzilla_trial.png)
