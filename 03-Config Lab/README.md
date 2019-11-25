#### AWS Config

1)  Go to the AWS Search Service bar and find *AWS Config*. Press *Get started*.

!{images](images/1f913f3da05e7bddd31bbe4f2ae66eff.png)

2)  In the *Settings* section make sure you select both options in *All
    resources* and make sure that a S3 bucket is configured to store the
    configuration history and configurations snapshot.

!{images](images/7b5b0af103e0179df544484801f14914.png)

3)  In the *SNS topic* provide a name for the new topic created. In this case
    *config-topic*, press *Next* once done.

!{images](images/036c0dde57bac060954ae8fc4ff8c332.png)

4)  Select the 3 rules highlighted below. Use the search bar to find them. Click
    *Next* once done.

!{images](images/a6966fb42a24a42322f3a8f6b6fcef18.png)

5).  Review the configuration page and click *Confirm*.

!{images](images/de37869ace958028cfeabed59551966a.png)

6)  You will wait a couple of minutes till the rules are set up.

!{images](images/92c267b2f113ff4908ef3ef5cbdf0862.png)

7)  Refresh the console to make sure that all the metrics are displayed on the
    console

!{images](images/b7f2e48c1c44f5f73eb79f7c7000a658.png)

8)  Once done you will see the following the dashboard

!{images](images/7d7b49f223c61764d8af1d1a00f597cb.png)

As we can see there is an alarm raised. This alarm states that we are not
streaming the CloudTrail logs to CloudWatch. Let’s proceed and remediate this
alarm.

9)  Go to CloudTrail console – to do so search CloudTrail in the AWS Search
    Service bar. Once on the console click on *View Trails* and click on the
    trail created previously.

10)  In the configuration page, under the CloudWatch Logs section press the
    *Configure*.

!{images](images/6ca4ad538d4c9721fa5ee1deaf09ea43.png)

11)  Leave the default log group suggested by the wizard and press *Continue*.

!{images](images/a857e16c7e873ae562fe0e594698d396.png)

12)  Press *Allow* to have an IAM role created to allow CloudTrail to push logs
    to CloudWatch.

!{images](images/28cbbb799d10a2c90b2d82e1aa524aad.png)

13)  Once created you will see the *Log group* and *IAM role* created in the
    CloudTrail configuration of the trail created earlier.

!{images](images/351dc23980958dc249d36d40ee4301e0.png)

14)  Now let’s go back to AWS Config and click on
    *cloud-trail-watch-logs-enabled*.

!{images](images/b2f084545b9dd8d85b38518c78ee719b.png)

15)  Click *Re-evaluate* to have AWS Config check if the corrective measures have
    been successfully applied

!{images](images/6135dc8f7b6170dd7e52af1695b18071.png)

16)  Refresh the console a couple of times. If the corrective measures have been
    successfully applied you will see that the alarm has disappeared.

!{images](images/abe46a92e787db537b7921389463db05.png)
