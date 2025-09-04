AWS Lambda Hello World

This project demonstrates how to create, build, and test an AWS Lambda function locally using AWS SAM CLI and Docker.

The function responds with "Hello from Lambda!" when accessed through a local API endpoint.

![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Python](https://img.shields.io/badge/Python_3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![AWS SAM CLI](https://img.shields.io/badge/AWS_SAM_CLI-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)

Prerequisites


AWS Account (no need to deploy yet)

Python 3.11

Docker Desktop

AWS SAM CLI

(Optional) Python virtual environment



Project Structure
aws-lambda-hello/
+-- hello_world/
¦ +-- app.py
¦ +-- requirements.txt
+-- template.yaml
+-- README.md

yaml


- `hello_world/app.py` ? Main Lambda function code.  
- `hello_world/requirements.txt` ? Python dependencies.  
- `template.yaml` ? AWS SAM template that defines the Lambda function and API Gateway.  

---

## Running Locally

1. **Build the Lambda function**  
   ```bash
   sam build --use-container --template template.yaml
Validate the template

bash

sam validate --template template.yaml
Invoke the Lambda locally

bash

sam local invoke HelloWorldFunction
Start local API Gateway

bash

sam local start-api
Test the endpoint
Open your browser or run:

bash

curl http://127.0.0.1:3000/hello
? Expected output:

json

{"statusCode": 200, "body": "Hello from Lambda!"}

Notes
Make sure Docker is running before building or invoking Lambda.
The folder structure is critical: hello_world/ must contain both app.py and requirements.txt.
SAM automatically handles dependencies during the build process.

License
This project is licensed under the MIT License.