# Lambda Layer Creation by GitHub Actions
## Introduction
This repository creates [Lambda Layers](https://docs.aws.amazon.com/lambda/latest/dg/configuration-layers.html) with NPM dependencies on the AWS cloud.

Instead of manually deploying Lambda Layers, this CI/CD pipeline automates the build and deployment process.

## Workflow
The [lambda-layer-creator.yml](https://github.com/kusumsiri/Lambda-Layer-Creator/blob/main/.github/workflows/lambda-layer-creator.yml) file handles the CD process.
It contains several steps as follows.
1. `actions/setup-node@v3` set up GitHub Actions workflow with node.js
2. `TheDoctor0/zip-release@0.4.1` used to create the release zip archive
3. `giboow/action-aws-cli@v1` AWS CLI GitHub action to push the lambda layer to AWS
## How to use
1. Fork this repository
2. Create IAM user [access keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html#Using_CreateAccessKey)
3. Set AWS_ACCESS_KEY_ID & AWS_SECRET_ACCESS_KEY secrets on repository settings
4. Edit the variable NPM_PACKAGES in the [action specification](.github/workflows/lambda-layer-creator.yml) according to need
5. As soon as push this change, the workflow will run and deploy the layer to  AWS

![Screenshot](Screenshot.png)
