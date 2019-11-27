### LAB 6 - AWS WAF

1)  Got to the AWS WAF console and select *Go to AWS WAF*.

![images](images/0364236d876a9d7f3448dc62b86b5a07.png)

2)  Click on *Configure web ACL*. The web ACL wizard will guide us through all
    the steps necessary to create the conditions and rules that are necessary
    that are needed in a Web ACL.

![images](images/6315d88b580feadaf3cbbe2a43c17b82.png)

3)  We will be presented the anatomy of a WEB ACL. Simply click *Next* at this
    stage.

![images](images/18a87f164555d20752e840e0974af67e.png)

4)  Fill in the Web ACL name, the region and the resource that you want the ACL
    to be associated with – in this case the ALB *techshift-alb*. Press *Next*
    once done.

![images](images/5df84e853387b8b00940119da16eea28.png)

5)  Now let’s create a condition. We will choose an *IP match condition* for
    this lab.

![images](images/c970cadfe67cb2279be629bef1a1d31d.png)

6)  Name the condition *My-IP* and add your public IP address in the list of IP
    addresses that will be filtered. You can find your public IP address on
    www.whatismyip.com.

![images](images/9e8707db1c7a1f607e0effbf66d13e8e.png)

7)  Ensure that the IP is properly added and press *Next*.

![images](images/8def2e31fdfdfa4262dc646bd5277499.png)

8)  In the rule section we will create a rule that will block the access of our
    public IP. Press on the *Create rule* button.

![images](images/580e92e0b6204a519b4a22fbcf67c850.png)

9)  Give the rule a name *Techshift-WAF-Rule-IP* and add a condition as listed
    below. Once done press *Create*.

![images](images/c68329c50ff322eb1bf657420262307e.png)

10)  Set the default action to allow all the request that do not match the
    condition as we want to block only our IP address. Press *Review and
    Create*.

![images](images/9b432e566aa0e1564d17a866d3017500.png)

11)  Once you verify the configuration click on *Confirm and Create* and wait for
    the ACL to be created.

![images](images/19ba22269e689a702d8adae366839f48.png)

Once the creation is completed go ahead and test it on your browser. You will
notice that you are not allowed to access you ALB.

![images](images/7205543d7b9f5e8b063fbe3a4b715446.png)

Try to access the ALB on your mobile phone. You should be able to access it.

Proceed to the [next lab (Anaylizing CloudTrail logs with Athena)](../07-CT-Athena-Lab/README.md)
