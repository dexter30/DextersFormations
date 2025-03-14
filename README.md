# Cloud formation project

These are files used to make cloud formation networks on AWS. 
This was part of a AWS restart course to develop skills on amazon systems. 

Here is a guide on how to utilise these in AWS

## Setting up a YAML script
AWS formation projects are written in either YAML or JSON. In this example we are using YAML. 

If you look in `Task2.yaml` file we have an example of how we cna set up an EC2 instance

#### Example EC2 Initialisation 

```
  Ec2Instance:
    Type: AWS::EC2::Instance
    Properties:
      ImageId: !Ref AmazonLinuxAMIID
      Tags:
        - Key: Name
          Value: Lab VPC
```

In this example we specify the type of resource we want. An EC2 instance `AWS::EC2::Instance` and underneath we specify the properties `ImageID` and `tags`. 

These are what we use to instantly initialise resources and their parameters.

We do this for the VPC, internet gateway etc. Everything we need for a vpc network. 

* `AWS::EC2::VPC`
* `AWS::EC2::InternetGateway`
* `AWS::EC2::Subnet`

For a full list of available services please check them out here https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html 

## Deploying to AWS
Once your script is ready you can use it as part of the AWS cloudformations. 

AWS console -> Services -> Cloud formations

* Click create Stack
  * When you create a stack in Cloudformations can upload your yaml file under `Upload a template file` option
  * This will generate the infrastructure design which you can confirm. 
  * Name your stack and continue with the options. 

This will generate a infrastructure project as specified in the YAML file. 

## The examples

`task1.yaml` will create a simple project with an S3 bucket. 

`task2.yaml` will create 2 EC2 instances and the second one uses a different specific imageID from amazon.