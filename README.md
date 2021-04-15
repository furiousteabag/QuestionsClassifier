# Questions Classifier

Classifying questions if they were prepared by expert or not.

## Files

- [task.pdf](task.pdf): task description
- [naive_approach.ipynb](naive_approach.ipynb): classic ml solutions to given problem
- [auto_encoder_approach.ipynb](auto_encoder_approach.ipynb): autoencoder solution to given problem
- [predict.py](predict.py): model prediction wrapper
- [data/](data/): initial and test data
- [models/](models/): our pretrained models
- [output/](output/): output submissions


## Overview of the approach

## Usage

Clone this repository:
```bash
git clone https://github.com/SmirnovAlexander/QuestionsClassifier.git
cd QuestionsClassifier/
```

In [Dockerfile](./Dockerfile) specify what model you want to use by selecting one from [models](./models) directory, e.g. `tfidfvectorizer__votingclassifier`:

```
CMD python predict.py ./models/tfidfvectorizer__votingclassifier.pickle ./data/test.csv
```

Afterward build docker container:

```bash
sudo docker build -t questions_classifier .
```

Then execute prediction and write its output to the file:

```bash
sudo docker run questions_classifier > ./sample_output.csv
```

Model loading part takes a bit, but once it is loaded making predictions is blazingly fast.

## Team

- [Penskaya Taisia](https://github.com/TayaPenskaya)
- [Dranoshuk Artem](https://github.com/Artem531)
- [Smirnov Alexander](https://github.com/SmirnovAlexander)
