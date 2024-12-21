## configure aws

install the aws cli

run:

```
aws configure
AWS Access Key ID [None]: fakeMyKeyId
AWS Secret Access Key [None]: fakeSecretAccessKey
Default region name [us-east-1]:
Default output format [None]:
```

test creds using:

```
aws dynamodb list-tables --endpoint-url http://localhost:8000
```

## run docker container for DDB

docker compose up

## setup DDB table

aws dynamodb create-table --table-name books --attribute-definitions AttributeName=id,AttributeType=S --key-schema AttributeName=id,KeyType=HASH --table-class STANDARD --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5 --endpoint-url http://localhost:8000

## run web service

deno run dev

## run frontend app

https://github.com/go-chi/chi

https://go.dev/doc/tutorial/getting-started
