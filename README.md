# Face Classifier

### Tools used

This was built with PyTorch/FastAI for the Machine Learning part and Flask as a Webserver. For containerization and easy deployment I use Docker. The dataset in use is the [The Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) but I chose to only use three of the pet types contained in there.

## How to use

You can easily use this as a step by step model.

### Training Model

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ZenoVka-Vestraq/FaceClassifier/blob/main/Train_a_Face_Recognition_Model.ipynb)

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

Command to launch the container:
```bash
docker build -t churros_samosa_classifier . && docker run --rm -it -p 5000:5000 churros_samosa_classifier
```

Then you can deploy the Container to any Cloud Provider of your choosing. 

I recommend [Render](https://render.com), which is what I used for my deployment but everything else should work fine, too. 



**Steps for deploying on Render**

- Fork this repository 

- Replace the model (export.pkl)

- Change the HTML and CSS to your liking

- In the Render Dashboard create a new Web Service

- Link your repository

- Make sure Docker is selected

- Done!
