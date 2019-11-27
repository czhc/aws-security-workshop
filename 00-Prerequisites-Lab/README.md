### Create a Cloud9 environment

1) Go to the Cloud9 console and press *Create environment*.

![prerequisites lab](images//1d057a6d465f25b6ff1842ee465ab08d.png)

2) Provide a name for your environment - you can name it ___TechShift___

![images/](images/cloud9-environment-name.png)

3) Leave all the parameters untouched and press *Next Steps*.


![images/](images/bd9d46e5b0a0c7f7e0e405566a2a4806.png)


4) Review the settings and press *Create environment*.


![images/](images/09e18a38e2942abbedcfae852c057fb3.png)


5) Now you have an IDE in the cloud.


![images/](images/6bf8fc54f1f01e9eda93a8dc95f5dccd.png)

6) Click on *Open IDE*

7)In the Terminal type teh following commands

```
git clone https://github.com/andyliza/aws-security-workshop.git

```
![images/](images/clone.png)

8) Once the repository is cloned, please depoloy the CloudFormation template using the following command:

```
aws cloudformation create-stack --template-body file://./aws-security-workshop/Cloudformation/security-workshop.json --stack-name bkksecuritychallenge2019 --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=InstanceType,ParameterValue=t2.small ParameterKey=KeyName,ParameterValue=TechShift-KeyPair ParameterKey=RDSPassword,ParameterValue=techshift2019 ParameterKey=RDSUsername,ParameterValue=admin ParameterKey=VPCCIDR,ParameterValue=172.4.0.0/16

```

9) Once the installation begins you can check the status of the deployement using this command:

```
aws cloudformation describe-stacks --stack-name bkksecuritychallenge2019 \
                                   --query 'Stacks[0].StackStatus'
                                   --output text
```

![images/](images/statuscheck.png)

10) When you see the operations has completed successfully move to the [first lab (CloudTrail)](/aws-security-workshop/01-CloudTrail-Lab/README.md)
