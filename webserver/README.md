# Overviews

Configure all resources required to spin up a web server that allows all traffic

## Steps

- Create EC2 keypair for ssh through the AWS UI. call it `main-key` and select `.pem` version. Click create and down the `main-key.pem` file

- Run `terraform apply` to create all the resources
- Visit the public IP through http protocol make sure the server runs

- cd into the directory contains `main-key.pem`. Usually it is in the `Download` folder

- run `chmod 400 main-key.pem` to give read permisison to the file
- run `ssh -i "main-key.pem" ubuntu@<instance public ipv4>` to ssh into the instance
