# Backend API

Written in Python with [FastAPI](https://fastapi.tiangolo.com/).

## Getting started

- To get started, we need to deploy resources to create DynamoDB / Bedrock resource. To deploy, please see [Deploy using CDK](../README.md#deploy-using-cdk).
- Create virtual environment on your local machine

```sh
cd backend
python3 -m venv .venv
source .venv/bin/activate
pip install -r ./requirements.txt
```

- Configure environment variables

```sh
export TABLE_NAME=AmoreConversationTable
export ACCOUNT=140751793732
export REGION=ap-northeast-3
export BEDROCK_REGION=us-west-2
export DOCUMENT_BUCKET=amore-documentbucket
export LARGE_MESSAGE_BUCKET=amore-bedrockchatstack-largemessagebucket
export USER_POOL_ID=ap-northeast-3_nsXtOcVt5
export CLIENT_ID=30mi47f1e583i1rlh5dv1rfh13
```

## Launch local server

```sh
uvicorn app.main:app  --reload --host localhost --port 8000
```

- To refer the specification, access to [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) for [Swagger](https://swagger.io/) and [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc) for [Redoc](https://github.com/Redocly/redoc).

## Unit test

```sh
python tests/test_bedrock.py
python tests/test_repositories/test_conversation.py
python tests/test_repositories/test_custom_bot.py
python tests/test_usecases/test_bot.py
python tests/test_usecases/test_chat.py
```
