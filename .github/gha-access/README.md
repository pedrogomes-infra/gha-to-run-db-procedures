# run-db-procedures-gha-access

Creates AWS IAM role with necessary permissions for GitHub Actions.

## Overview

- AWS CF stack - creates IAM role

## Usage

### create/update

#### CF stack with IAM role

To create you need to run follows command:

```sh
npm run deploy [-- --aws-profile <AWS_ACCOUNT>]
```

This command will deploy CloudFormation stack with IAM role that has all needed permissions by GitHub Actions.
The IAM service is not bounded to any region, for that reason this stack creates global user `run-db-procedures-gha-access`.
The environment/stage and region are hardcoded (env: `global`, region: `us-east-1`) and must not be changed on deployment.
The permissions that are applied to the IAM user are working in every region and for any environment/stage.
