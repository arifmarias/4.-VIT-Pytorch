Vision Transformer (VIT) Implementation in pytorch on mnist images on textures
========

This repository implements [Vision Transformer](https://arxiv.org/abs/2010.11929) on a synthetic dataset of mnist colored numbers on textures/solid background .


## Sample from dataset

<img src="https://github.com/explainingai-code/VIT-Pytorch/assets/144267687/6a60022e-b6f6-4037-9839-c62fa7cabaf2" width="300">


## Data preparation
For setting up the mnist dataset:
Follow - https://github.com/arifmarias/4. VIT-Pytorch#data-preparation

Download Quarter RGB resolution texture data from [ALOT Homepage](https://aloi.science.uva.nl/public_alot/)
In case you want to train on higher resolution, you can download that as well and but you would have to create new imdb.json
Rest of the code should work fine as long as you create valid json files.

Download imdb.json from [Drive](https://drive.google.com/file/d/1dtbFhDCDJVp4OYlAzhVY_mzWTkrYrFlt/view?usp=sharing)
Verify the data directory has the following structure after textures download
```
VIT-Pytorch/data/textures/{texture_number}
	*.png
VIT-Pytorch/data/train/images/{0/1/.../9}
	*.png
VIT-Pytorch/data/test/images/{0/1/.../9}
	*.png
VIT-Pytorch/data/imdb.json
```

# Quickstart
* Create a new conda environment with python 3.8 then run below commands
* ```git clone https://github.com/arifmarias/4. VIT-Pytorch.git```
* ```cd VIT-Pytorch```
* ```pip install -r requirements.txt```
* ```python -m tools.train``` for training vit
* ```python -m tools.inference``` for running inference, attention visualizations and positional embedding plots

## Configuration
* ```config/default.yaml``` - Allows you to play with different aspects of VIT 


## Output 
Outputs will be saved according to the configuration present in yaml files.

For every run a folder of ```task_name``` key in config will be created 
* Best Model checkpoint in ```task_name``` directory

During inference the following output will be saved
* Attention map visualization for sample of test set in ```task_name/output``` 
* Positional embedding similarity plots in  ```task_name/output/position_plot.png```


## Sample Output for VIT 

Following is a sample attention map that you should get

<img src="https://github.com/explainingai-code/VIT-Pytorch/assets/144267687/76d63318-478f-41aa-a321-e907c29e26fb" width="300">

Here is a positional embedding similarity plot you should get

<img src="https://github.com/explainingai-code/VIT-Pytorch/assets/144267687/0ba9afa7-1d5d-4cbc-8b9d-0a4367e9f9ed" width="300">


## Citations
```
@misc{dosovitskiy2021image,
      title={An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale}, 
      author={Alexey Dosovitskiy and Lucas Beyer and Alexander Kolesnikov and Dirk Weissenborn and Xiaohua Zhai and Thomas Unterthiner and Mostafa Dehghani and Matthias Minderer and Georg Heigold and Sylvain Gelly and Jakob Uszkoreit and Neil Houlsby},
      year={2021},
      eprint={2010.11929},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```



