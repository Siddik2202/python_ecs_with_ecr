# Deploy Your Application on AWS ECS

## Steps to be perform

* You need to upgrade your flask in dockerfile check befor run. 

1. Craete a Cluster on AWS ECR Panel by giving Name and AWS Farget.

2. For docker image we need to create private/public repository from Amazon ECR by giving name.

3. Login yor AWS ECS docker using
     aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin [339713170737.dkr.ecr.ap-south-1.amazonaws.com] / private url without repo name

4. Create your Dockerfile on your root file. And build image by using
     docker build -t 339713170737.dkr.ecr.ap-south-1.amazonaws.com/demo-app-repo:latest .

5. After built your image push your AWS ECR repository by usng then you can seeimage under repository.
    docker push 339713170737.dkr.ecr.ap-south-1.amazonaws.com/demo-app-repo:latest

6. Now you need to create Task defination (which work as a pod which reponsible for runing container)

7. Now giving name and set cpu as per need, give container name and image url, port where you app run then create.

8. After createing Task defination run task from deploy. And select your cluter now AWS manage by yourself 

9. And you deploy Successfully your application on AWS using ECS and ECR.
