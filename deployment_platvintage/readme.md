# Deployment FastAI model using [Starlette](https://www.starlette.io/), [Docker](https://www.docker.com/) and  [Zeit](https://zeit.co/)
This folder contains all the necessary code required to deploy our Plant disease detection model built in [this notebook](https://github.com/aayushmnit/fastai_v3_experimentation/blob/master/Lesson-1-PlantVintage.ipynb) using the [Now](https://zeit.co/now) service from [Zeit](https://zeit.co/). 

## Deploying on Ziet
Following instructions are taken from [FastAI deployment guide for Zeit](https://course-v3.fast.ai/deployment_zeit.html).

### One-time setup
Install Now;s CLI(Command line interface)
```bash
sudo apt install npm # if not already installed
sudo npm install -g now
```

### Deploy
On the terminal, make sure you are in the zeit directory, then type:
```bash
now
```
The first time you run this, it will prompt for your email address and create your Now account for you. After your account is created, run it again to deploy your project.

Every time you deploy with now it’ll create a unique deployment URL for the app. It has a format of xxx.now.sh, and is shown while you are deploying the app. When the deployment finishes and it shows ”> Success! Deployment ready” on the terminal, type in the terminal:
```bash
export NAME='changeme:this-is-your-name-for-the-url'
now alias $NAME
```
This will alias the above mentioned deployment URL to $NAME.now.sh. You can do this everytime after you deployed. With that, you have a single URL for your app.

### Scaling
By default all deployment goes to sleep after some inactive time. This is not good for the latest version of your app. So do this:

```bash
# You only need to do this once.
now scale $NAME.now.sh sfo 1
```

### Test the URL of your working app
Go to $NAME.now.sh in your browser and test your app.

## Local Testing 
In case you want to run the app server locally, run the following command
```python
python app/server.py serve
```

Go to http://localhost:5042/ to test your app locally.