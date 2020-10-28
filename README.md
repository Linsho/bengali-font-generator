# bengali-font-generator

## build

```
docker build -t bengali-font-generator:latest docker
```

## run 

```
docker run -v $PWD:/base -p 8888:8888 --rm bengali-font-generator:latest
```
will launch jupyter notebook.

1. Download the dataset from https://www.kaggle.com/c/bengaliai-cv19/overview and place it in `bengaliai-cv19`.
2. Download any of the .ttf format font files for Bengali and place them in `input/fonts/`.
3. Open the `data_generator.ipynb` and run it.
