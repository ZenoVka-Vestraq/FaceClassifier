# Pet Recognition Classifier

### Tools used

This was built with PyTorch/FastAI for the Machine Learning part and Flask as a Webserver. For containerization and easy deployment I use Docker. The dataset in use is the [The Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) but I chose to only use three of the pet types contained in there.

## How to use

You can easily use this as a step by step model.

### Training Model

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ZenoVka-Vestraq/Pet-Recognition-Classifier/blob/main/Train_a_Pets_Recognition_Model.ipynb)

Open the Notebook in Colab above. Most steps will be described in detail there.

Decide which types of pets to classify by changing:

```python
#Deciding which pet types we want to classify
labelA = 'pug'
labelB = 'scottish_terrier'
#etc
```

At the end of the notebook there will be a download for the export.pkl file, which is the result model. 

### Deploying the Model

Command to launch the container inside VSCode terminal:
```bash
docker build -t pet_recgonition_classifier . ; docker 
run --rm -it -p 5000:5000 pet_recognition_classifier
```

Deploying the Container to [Render](https://render.com)/



**Steps for deploying on Render**

- In the Render Dashboard create a new Web Service

- Link repository

- Select Docker
