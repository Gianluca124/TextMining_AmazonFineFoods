# Text classification and Text clustering on Amazon Fine Food Reviews dataset

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

## Table of contents
* [Abstract](#abstract)
* [Report](https://www.slideshare.net/GianlucaCavallaro3/text-mining-on-amazon-fine-foods-reviews)
* [Requirements](#requirements)
* [COVIDx CXR-3: Dataset and Image Pre-processing](#covidx-cxr-3-dataset-and-image-pre-processing)
* [AC-GAN Training and Generation](#ac-gan-training-and-generation)
* [AC-GAN Evaluation: FID, Intra FID, Inception Score (IS), t-SNE](#ac-gan-evaluation-fid-intra-fid-inception-score-is-t-SNE)
* [Chest X-Ray Classification: Pneumonia and COVID-19 detection with GAN augmentation](#chest-x-ray-classification-pneumonia-and-covid-19-detection-with-gan-augmentation)
* [Status](#status)
* [Contact](#contact)
* [License](#license)
* [Contributing](#contributing)

## Abstract

In this project, different text mining techniques are applied to the Amazon Fine Food Reviews dataset. In particular, the tasks of text classification and text clustering are addressed. The main questions that are being investigated are:

1) Is it possible to classify the reviews as "good" or "bad"?
2) 2) Is it possible to predict the score assigned to the review from the text of the review itself?
3) 3) Is it possible to group similar reviews into the same cluster?

![GenetationExample](https://github.com/giocoal/CXR-ACGAN-chest-xray-generator-covid19-pneumonia/raw/main/Report/CXR-ACGAN%20-%20Example.png)

## Requirements

- python==3.8
- ipython
- ipykernel
- matplotlib
- pandas
- seaborn
- tqdm==4.64.1
- scikit-learn==1.2.0
- glob2==0.7
- keras==2.10.0
- Keras-Preprocessing==1.1.2
- numpy==1.24.2
- opencv_python==4.7.0.68
- pandas==1.5.3
- Pillow==9.4.0
- imageio==2.25.0

## COVIDx CXR-3: Dataset and Image Pre-processing

### Step 1. Download and extract the dataset

Download COVID-x CXR-3 from the [official Kaggle Folder](https://www.kaggle.com/datasets/andyczhao/covidx-cxr2?select=competition_test) and extract `train` and `test` folders in `./Data/COVIDx/`, resulting in a folder tree like this:

```
project_folder
└───Data
    ├───COVIDx
    |    ├───test_COVIDx9A.txt
    |    ├───train_COVIDx9A.txt
    |    ├───train
    |    └───test
    ├───COVIDx-splitted-resized-112
    ├─── ...
```

### Step 2. Perform class splitting of the dataset
Run the `./Data/train_test_class_split.sh` bash script which will subdivide the training and testing images within the COVIDx-splitted-resized-112 folder according to their class. So that we can then use `flow_from_directory`. You get a directory tree like this:
```
project_folder
└───Data
    ├───COVIDx
    ├───COVIDx-splitted-resized-112
    |    ├───test_COVIDx9A.txt
    |    ├───train_COVIDx9A.txt
    |    ├───train
    |    |   ├───COVID-19
    |    |   ├───normal
    |    |   └───pneumonia
    |    └───test
    ├─── ...
```


### Step 3. (Opt) Perform images resizing to 112 x 122
This step is intended to reduce the size of the dataset. It is not essential because resizing is also performed in the training phase. Run the `./Data/resize_all.py` script.

## AC-GAN Training and Generation

1. Run the code and follow the detailed instructions in `AC-cGAN-training.ipynb` to perform AC-GAN training.
2. Generates images in large quantities using `AC-cGAN-generator.ipynb`.

## AC-GAN Evaluation: FID, Intra FID, Inception Score (IS), t-SNE

Run the code and follow the detailed instructions in `AC-cGAN-evaluate.ipynb` to:
- Displaying training metrics (**Losses and Accuracies**)
- Calculate **Fréchet inception distance (FID)**
- Calculate the **Intra Fréchet inception distance (Intra FID)**
- Calculate the **Inception Score (IS)**
- View **t-SNE two-dimensional embeddings**

## Chest X-Ray Classification: Pneumonia and COVID-19 detection with GAN Augmentation

Use the notebooks in `CXR Classification` folder to train and evaluate classification models for the detection of COVID-19, Pneumonia and Absence of symptoms in Chest X-ray. Some forms of data augmentation are tested, including generation by trained AC-GAN. 

## Status

 Project is: ![##c5f015](https://via.placeholder.com/15/c5f015/000000?text=+)  _Done_


## Contact

[Giorgio Carbone](https://github.com/giocoal) - feel free to contact me!


## License
* >You can check out the full license [here](https://github.com/giocoal/CXR-ACGAN-chest-xray-generator-covid19-pneumonia/blob/main/README.md)

This project is licensed under the terms of the **MIT** license.

## Contributing

1. Fork it (<https://github.com/giocoal/CXR-ACGAN-chest-xray-generator-covid19-pneumonia.git>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request


# Contributors

* [Giorgio Carbone](https://github.com/giocoal)
* [Remo Marconzini](https://github.com/rmarconzini)
* [Gianluca Cavallaro](https://github.com/Gianluca124)    
