# Generating credentials for Designer connectors on CP4i

[Return to main lab page](../index.md)

## MQ Connector
# 1. Configure your MQ <a name="introduction"></a>
First we will create a new queue in our Qmgr and capture the info needed to connect to our Qmgr from ACE Designer. 
First from your dashboard we will open your qmgr instance.   Right click on the Messaging Qmgr and open in new tab.

![alt text][pic1]

 You will see your Qmgr name.  In this example it is CMQGR15.   Click on the Create a queue so we can create the queues to use in our labs.

![alt text][pic2]

Now click on the Local queue tile. 

![alt text][pic3]

Now enter the Queue Name and then add text into the Description.  Once done with that leave the rest of the defaults and click on Create.

**Note:** while here we will also create a queue for the ServiceNow lab should you decide to do that one as well.   Just change SALESFORCE to SERVICENOW

![alt text][pic4]

You will see in the upper right part of the sreen the green pop-up that shows your queue was created.   Click on the x in the window to close it.  Then click on the Manage tile for your QMgr.  

![alt text][pic5]

Now you will see varies information about your running Qmgr.   You will also see your new queue you just created and it will show the queue depth of 0/5000.  This means 0 messages and the queue is configured to handle a total of 5000 messages.

NOTE: Leave this tab open and we will use it to view messages as we put them on the queue.   

![alt text][pic6]

[pic1]: images/mq-conf1.png
[pic2]: images/mq-conf2.png
[pic3]: images/mq-conf3.png
[pic4]: images/mq-conf4.png
[pic5]: images/mq-conf5.png
[pic6]: images/mq-conf6.png

# 2. Go into Redhat Open shift to get host info and set security.

Now we will login to the RedHat console to get the needed host for the Qmgr and also set the security for the Qmgr. 
You will receive the URL for the console that you are working on from the instructor and should be similar to the following which is for the chopper cluster.

<code>
    https://console-openshift-console.apps.chopper.coc-ibm.com/dashboards
</code>

Login to the console using the credentials that were provided to you from the insturctor.  In this example we are using chopper15.   

![alt text][pic7]

Follow the following steps:
1. In the left menu select Routes under Networks. 
2. Make sure that the Project in the top menu matches your login credentials.  In this example the Project is chopper15 (this is also called your Namespace)
3. In the upper right corner you should see your login id
4. Next click on the route (RT) for your Qmgr.

![alt text][pic8]

This will show you the Route details.  Scroll down the page to the service.   That will be used for the host name when connecting to this Qmgr. 

In this example we have **qmgr15-ibm-mq** add your userid and extension of svc. 
So for this Qmgr the host will be **qmgr15-ibm-mq.chopper15.svc**

![alt text][pic9]

Now we will go to the Qmgr running Pod.   Under Workloads click on Pods.    This will show you all your running pods.  Make sure you are still in Project that matches your login.  
You should see a pod running called qmgr and ending in mq-0.   In this example we have **qmgr15-ibm-mq-0**.   Click on that and you will be taken to the Pod details. 
Next click on Terminal in the menu bar which will open a command window to this pod.  
Type the MQ command **runmqsc** this will connect to the MQSC command line interface for the Qmgr. 

Enter the following commands from the terminal. 

<code>
    ALTER QMGR CHLAUTH (DISABLED)
    ALTER AUTHINFO(SYSTEM.DEFAULT.AUTHINFO.IDPWOS)  AUTHTYPE(IDPWOS) CHCKCLNT(NONE)
    REFRESH SECURITY TYPE(CONNAUTH)
</code>


![alt text][pic10]

So from this lab we have created the needed MQ Queues, and also have the hostname for our Qmgr.   We will need this info when we run the Event Driven flow labs.   

[Return to main lab page](../index.md)


[pic7]: images/mq-sec1.png
[pic8]: images/mq-svc2a.png
[pic9]: images/mq-svc3.png
[pic10]: images/mq-sec2.png