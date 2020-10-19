# Flask Starter App

A barebones Flask app, which can easily be deployed to Heroku.

This is a template repository, you can [generate your own](https://github.com/dolugen/flask-starter/generate) from this.

Adapted from [heroku/python-getting-started](https://github.com/heroku/python-getting-started).


![Heroku and Flask](header.png)

## Running Locally

Make sure you have Python 3.7 [installed locally](http://install.python-guide.org). To push to Heroku, you'll need to install the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli).

```sh
$ git clone https://github.com/dolugen/flask-starter.git
$ cd flask-starter

$ python3 -m venv env
$ source ./env/bin/activate
$ pip install -r requirements.txt

$ heroku local
```

Your app should now be running on [localhost:5000](http://localhost:5000/).

## Testing

```
$ pytest tests.py
```

## Deploying to AWS Elastic Beanstalk

**Prerequisites: Python 3.7.9, pip, and awsebcli**

You also need your AWS credentials ready in your `~/.aws/credentials` file.

### Initialize new EB app

When starting a new deployment, run:

```
eb init
```

The command will start an interactive session where you:

- Enter the app name
- Choose Python version to use
- Choose AWS region

### Create new environment for deployment

This will create a new environment, and deploy the app there.

```
eb create env-name
```

### Open deployment

Once deployed, open the app in a browser window:

```
eb open
```

### Set environment variables

You can set configuration values such as `MAPBOX_ACCESS_TOKEN` using:

```
eb setenv KEY=value KEY2=value2
```

### Monitoring deployment

Here are some helpful commands to monitor your deployment:

```sh
# show health status of envs
eb health

# show logs
eb logs

# print environment variables
eb printenv

# shows environment status and info
eb status
```


## Deploying to Heroku

```sh
$ heroku create
$ git push heroku master

$ heroku open
```
or

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

## Documentation

For more information about using Python on Heroku, see these Dev Center articles:

- [Python on Heroku](https://devcenter.heroku.com/categories/python)
