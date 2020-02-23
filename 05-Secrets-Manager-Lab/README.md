#### To create and store your secret

1) Sign in to the AWS Secrets Manager console

2) On either the service introduction page or the secrets list page,
    choose **Store a new secret**.

3) On the **Store a new secret** page, choose **Credentials for Database**.
    Fill in the following values: 
    User name: `admin`
    Password: `securityID2020`
    Encryption Key: `security-id`
    Database: `securityimmersiondaystack-rd-...`
    
    ![images](images/62ee37a962c8d96713af8b33f510fe6d.png)

4)  Give the *Secret* a name – *securityid/demo/auroradb*. Add a description and
    press *Next*.

![images](images/8625b77cdb1bb9b3ac03fb8c97b92836.png)

5)  Enable automatic rotation for 30 days using a Lambda function and name it
    `aurora-secret-rotate` and press *Next*.

![iamges](images/6b319d5df7d49e8c19e7b662969e2954.png)

6)  In the review page press *Store*.

![iamges](images/5394a066ef14f52afd154cf9e8bdf262.png)

#### To retrieve your secret in the AWS Secrets Manager console

1) On the secrets list page, choose the name of the new secret that you created
    in the previous section.

>   The details page for your secret appears.

2) In the **Secret value** section, choose **Retrieve secret value**.

3) You can view your secret as either key-value pairs, or as a JSON text
    structure.

#### To retrieve your secret in the AWS Secrets Manager from CLI

1) Go to your Cloud9 Console created in the previous labs.

![iamges](images/aac310e46025be2783c389fae31b32b3.png)

2)  In the console type the following commands:

```
   aws secretsmanager describe-secret --secret-id securityid/demo/auroradb

```

The output will look like this:

```
{
    "Name": "securityid/demo/auroradb", 
    "VersionIdsToStages": {
        "f989cabb-6c54-4ee5-a939-2a72a34b3689": [
            "AWSPENDING"
        ], 
        "6aff56cd-6c64-401c-b3da-e24485d898d3": [
            "AWSCURRENT"
        ]
    }, 
    "Tags": [], 
    "RotationRules": {
        "AutomaticallyAfterDays": 30
    }, 
    "LastChangedDate": 1582441450.399, 
    "KmsKeyId": "arn:aws:kms:us-east-1:<ACCOUNT_ID>:key/<KEY_UUID>", 
    "RotationEnabled": true, 
    "LastAccessedDate": 1582416000.0, 
    "ARN": "arn:aws:secretsmanager:us-east-1:<ACCOUNT_ID>:secret:securityid/demo/auroradb-HP6Bcj", 
    "RotationLambdaARN": "arn:aws:lambda:us-east-1:<ACCOUNT_ID>:function:SecretsManageraurora-secret-rotate"
}
```
...and the command:

```
   aws secretsmanager get-secret-value --secret-id techshift/demo/aurora --version-stage AWSCURRENT
```
The output will look like this:

```
{
    "Name": "securityid/demo/auroradb", 
    "VersionId": "6aff56cd-6c64-401c-b3da-e24485d898d3", 
    "SecretString": "{\"username\":\"admin\",\"password\":\"securityID2020\",\"engine\":\"mysql\",\"host\":\"securityimmersiondaystack-rdscluster-1ipeamna53vil.cluster-cwi091zkedko.us-east-1.rds.amazonaws.com\",\"port\":3306,\"dbClusterIdentifier\":\"securityimmersiondaystack-rdscluster-1ipeamna53vil\"}", 
    "VersionStages": [
        "AWSCURRENT"
    ], 
    "CreatedDate": 1582441303.964, 
    "ARN": "arn:aws:secretsmanager:us-east-1:<ACCOUNT_ID>:secret:securityid/demo/auroradb-HP6Bcj"
}```
Proceed to the [next lab (WAF Lab)](../06-WAF-Lab/README.md)
