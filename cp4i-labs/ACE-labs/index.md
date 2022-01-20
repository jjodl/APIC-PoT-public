## Introduction
The labs are grouped under varies Experience and in each Experience you will see various labs.  We will cover both the ACE Toolkit and ACE Designer to build integrations. We will be creating APIs with Designer and then also importing them into APIC.   Will also cover labs on Event Streams(Kafka), Asset Repository and Operations Dashboard for tracing. 

[Return to Integration page](../index.md)

**[Complete the Setup insturctions for the VDI:](Setup/index.md)**
Follow these setups to show you how to connect to the assigned VDI you received from the instructor.  This will be needed for labs that are using the App Connect Enterprise Toolkit as well as some of the MQ labs.   
Also if your company has VPN settings that blocks unsigned certifications and you can't add an exception then you should do all the labs using the browser in the VDI.

**[Initial MQ setup](MQ-Pre-Lab/MQ-Pre-Lab.md)**
The initial MQ setup should be done before starting labs since several labs use MQ and this will disable MQ security and get you the hostname of the MQ QMgr running under your cluster-id.  

## Lab Abstracts

|  Subject                            | Description                                            |                                                               
|-----------------------------|------------------------------------------------------------------------------------------------------------|
| [Toolkit Experience](Toolkit-Experience/index.md)       | **Basic PING flow with Toolkit** This is a basic toolkit lab that you will create a simple Ping flow and then test locally and deploy to the ACE runtime in CP4I. 
|-----------------------------|------------------------------------------------------------------------------------------------------------|
| [SalesForce Experience](SF-Experience/index.md)       | **Multi-Style Integration with IBM App Connect and IBM API Connect the SalesForce experience**  Create no-code integrations using IBM App Connect and expose and manage the APIs created with IBM API Connect.
|-----------------------------|------------------------------------------------------------------------------------------------------------|
| [ServiceNow Experience](SN-Experience/index.md)       | **Multi-Style Integration with IBM App Connect and IBM API Connect the ServiceNow experience**  Create no-code integrations using IBM App Connect and expose and manage the APIs created with IBM API Connect.
|-----------------------------|------------------------------------------------------------------------------------------------------------|
| [Add on features](Add-on/index.md)       |**IBM Cloud Pak for Integration Add-on Experience** Hands on with Asset Repoitory which will allows you to store, manage, retrieve and search integration assets.  Also try the Operations Dashboard that provides cross-component transaction tracing to allow troubleshooting and investigating errors and latency issues across integration capabilities to ensure applications meet service level agreements.
|-------------------------|------------------------------------------------------------------------------------------------------------|
| [Kafka Experience](Kafka-Experience/index.md)       |**Event Driven flows (Kafka)** The purpose of this lab is to provide an introduction Kafka labs using Toolkit and Designer.
