# MLCAS2021teamQU

This is the code for [MLCAS2021 Crop Yield Prediction Challenge](https://eval.ai/web/challenges/challenge-page/1251/overview).

The directory structure is shown below.
```
├─input
│ ├ Training
│ ├ Test Inputs
│ └ clusterID_genotype
├─exp006
├─Dockerfile
├─docker-compose.yml
└─.dockerignore
```

After installing docker and docker-compose, launch the container with the following code.

```
docker-compoese up --build
```

The code is main.ipynb in exp006.

# Solution

Model
* [lightGBM](https://lightgbm.readthedocs.io/en/latest/)
* 10 seed averaging

Features
* Weather Features
   * statistical features(Maximum, Minimum, Mean, Median, Standard deviation, Skewness)
* Other Features
   * Ordinal Encoding
   * Count Encoding
   * Target Encoding(only Genotype ID, Location)
* Combine multiple features(Combine other features into a new variable)
   * Ordinal Encoding
   * Count Encoding

Cross Validation
* StratifiedKFold(Genotype ID)
