# MLflow-Basic

### dagshub
[dagshub](https://dagshub.com/)

MLFLOW_TRACKING_URI=https://dagshub.com/robinyUArizona/MLflow-Basic.mlflow \
MLFLOW_TRACKING_USERNAME=robinyUArizona \
MLFLOW_TRACKING_PASSWORD=292f6d1bdcfe7ac283b512eb8f2fccfce1733a51 \
python script.py

Run this to export as env variables:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/robinyUArizona/MLflow-Basic.mlflow

export MLFLOW_TRACKING_USERNAME=robinyUArizona 

export MLFLOW_TRACKING_PASSWORD=292f6d1bdcfe7ac283b512eb8f2fccfce1733a51

```

# MLflow on AWS



## MLflow on AWS Setup:

1. Login to AWS console.
2. Create IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo pip3 install pipenv

sudo pip3 install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell


## Then set aws credentials
aws configure


# Finally
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-robins-bucket

#open Public IPv4 DNS to the port 5000


#set uri in your local terminal and in your code 
export MLFLOW_TRACKING_URI=http://ec2-44-220-146-6.compute-1.amazonaws.com:5000/
```


