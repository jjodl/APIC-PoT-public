# Set MQ security and get hostname info for labs

There are several labs that use MQ and we will need to set security and get the hostname info to use in the varies labs. 
We will do this in the Openshift console and in the labs you will use the MQ console to create queues and view messages. 

[Return to main lab page](../index.md)

# 1. Go into Redhat Open shift to get host info and set security.

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

This will show you the Route details.  Scroll down the page to the service.   That will be used for the host name when connecting to this Qmgr. In this example the MQ hostname will be **qmgr15-ibm-mq**. 
Save this for when you setup MQ connecter in the App Connect Designer.

![alt text][pic9]

Now we will go to the Qmgr running Pod.   Under Workloads click on Pods.  This will show you all your running pods.  Make sure you are still in **Project** that matches your login.  
You should see a pod running called qmgr and ending in mq-0.   In this example we have **qmgr15-ibm-mq-0**.   Click on that and you will be taken to the Pod details. 
Next click on Terminal in the menu bar which will open a command window to this pod.  
Type the MQ command **runmqsc** this will connect to the MQSC command line interface for the Qmgr. 

Enter the following commands from the terminal. 

    ALTER QMGR CHLAUTH (DISABLED)
    ALTER AUTHINFO(SYSTEM.DEFAULT.AUTHINFO.IDPWOS) AUTHTYPE(IDPWOS) CHCKCLNT(NONE)
    REFRESH SECURITY TYPE(CONNAUTH)

![alt text][pic10]

So now we have disabled MQ security and have the hostname for our Qmgr.   

[Return to main lab page](../index.md)


[pic7]: images/mq-sec1.png
[pic8]: images/mq-svc2a.png
[pic9]: images/mq-svc3.png
[pic10]: images/mq-sec2.png