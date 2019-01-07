# Deployment FastAI model using [Starlette](https://www.starlette.io/), [Docker](https://www.docker.com/) and  Google App Engine
This folder contains all the necessary code required to deploy our Plant disease detection model built in [this notebook](https://github.com/aayushmnit/fastai_v3_experimentation/blob/master/Lesson-1-PlantVintage.ipynb) using Docker and  Google App Engine 

## Deploying on Google App Engine
Detailed instructions to setup your account first are described on [FastAI deployment guide for Gpogle App Engine](https://course-v3.fast.ai/deployment_google_app_engine.html).

Once you have setted up your Google Cloud SDK. Just open Google cloud SDK, cd into deployment_platvintage directory and run the following command -

```bash
gcloud app deploy
```

## Local Testing 
In case you want to run the app server locally, run the following command
```python
python app/server.py serve
```
You will be presented with a screen showing “Services to deploy”, enter Y.
It will take 8~10 minutes for app engine to deploy your docker based app and provide you the app URL. 

## Test the URL of your working app

To see your final app open http://YOUR_PROJECT_ID.appspot.com or run the following command in browser shell to launch your app in the browser:

```bash
gcloud app browse
```

Go to http://localhost:8080/ to test your app locally.