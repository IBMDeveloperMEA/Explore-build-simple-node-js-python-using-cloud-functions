# Explore and Build Simple Node.js and Python apps using Cloud Functions

## Workshop Resources

- Login/Sign Up for IBM Cloud [Here](https://cloud.ibm.com/registration?utm_medium=Inpersondirected&utm_content=000039JL&utm_term=10010797&utm_id=Aug2021-buildasimpleserverlesshelloworldnodejsappusingcloudfunctions-eventid-60ff224614ed545018eec011-global-devadvgrp-dubai-hybrid-workshop-dubai)
- [Presentation slides]()
- Workshop Replay [Here](https://www.crowdcast.io/e/serverless-hello-world)
- [Survey](https://www.surveygizmo.com/s3/6083679/528d6be4e0fd?uid=60ff224614ed545018eec011)<br/>

- Serverless Q&A [Here](ibm.biz/serverlessQA)
- IBM Cloud Functions[Pricing](https://cloud.ibm.com/functions/learn/pricing)
- IBM Cloud Functions [Limitations](https://cloud.ibm.com/docs/openwhisk?topic=openwhisk-limits)
- Our [Meetup Page](https://www.meetup.com/IBM-Cloud-MEA/)

### **Sign-up/Login to IBM Cloud**
  
There are 3 steps to create your account on [IBM Cloud](https://cloud.ibm.com/registration?utm_medium=Inpersondirected&utm_content=000039JL&utm_term=10010797&utm_id=Aug2021-buildasimpleserverlesshelloworldnodejsappusingcloudfunctions-eventid-60ff224614ed545018eec011-global-devadvgrp-dubai-hybrid-workshop-dubai): <br>
1- Put your email and password. <br>
2- You get a verification link with the registered email to verify your account. <br>
3- Fill the personal information fields. <br>
** Please make sure you select the country you are in when asked at any step of the registration process.
  
<img width="1188" alt="Screen Shot 2021-05-31 at 11 25 01 AM" src="https://user-images.githubusercontent.com/15332386/120156441-0769d980-c203-11eb-8cb3-29f4a8d5616a.png">

## Tutorial
  _Serverless computing_ refers to a model where the existence of servers is entirely abstracted away. Even though servers exist, developers are relieved from the need to care about their operation. They are relieved from the need to worry about low-level infrastructural and operational details such as scalability, high-availability, infrastructure-security, and other details. Serverless computing is essentially about reducing maintenance efforts to allow developers to quickly focus on developing code that adds value.

Serverless computing simplifies developing cloud-native applications, especially microservice-oriented solutions that decompose complex applications into small and independent modules that can be easily exchanged.

Serverless computing does not refer to a specific technology. Instead, it refers to the concepts underlying the previously described model. Some promising solutions like [Apache OpenWhisk](https://openwhisk.apache.org/) have recently emerged that ease development approaches used in the serverless model.

[IBM Cloud Functions](https://cloud.ibm.com/functions/?cm_sp=ibmdev-_-developer-tutorials-_-cloudreg) is a function-as-a-service (FaaS) platform on IBM Cloud, built using the Apache OpenWhisk open source project, that allows you to execute code in response to an event.

It provides a serverless deployment and operations model. With a granular pricing model that works at any scale, you get exactly the resources you need – not more, not less – and you are charged for code that is really running. The flexible programming model includes support for languages like JavaScript, Swift, Python, and Java, and support for running custom logic through Docker containers. This programming model allows small agile teams to reuse existing skills and to develop in a fit-for-purpose fashion. IBM Cloud Functions also includes tools to declaratively chain together the building blocks you develop. You can chain microservices to form workflows through composition. It is open and can run anywhere to avoid any kind of vendor lock-in.

## Estimated time

Completing this tutorial should take about 45 minutes.

## Prerequisites

To complete this tutorial, you will need an IBM Cloud account. If you don't have an existing account, visit the [Setting up your IBM Cloud account](https://cloud.ibm.com/docs/account?topic=account-account-getting-started&cm_sp=ibmdev-_-developer-tutorials-_-cloudreg) documentation for detailed instructions.

## Steps

Here are the steps required to complete this tutorial.

1. [Create an action](#1-create-an-action)
2. [Invoke with parameters](#2-invoke-with-parameters)
3. [Create a trigger](#3-create-a-trigger)
4. [Create a web action](#4-create-a-web-action)

### 1. Create an action

There are two main options to get started with IBM Cloud Functions. With both, you work with basic entities by creating, updating, and deleting actions, triggers, rules, and sequences.

With the command line interface, you perform these basic operations from the shell. With the IBM Cloud Functions user interface, you perform the same operations from your browser. This tutorial uses the browser user interface.

1. Log in to you [IBM Cloud](https://cloud.ibm.com?cm_sp=ibmdev-_-developer-tutorials-_-cloudreg) account.

1. Click the **Navigation Menu** icon.

    <img width="960" alt="1" src="https://user-images.githubusercontent.com/15332386/130031923-aa2cc7f1-0640-45fe-bb54-1e16cdc2043a.png">

1. Click **Functions** from the menu to access IBM Cloud Functions, the cloud-native development experience on IBM Cloud.

    <img width="120" alt="2" src="https://user-images.githubusercontent.com/15332386/130031934-da67ed4a-f72a-4236-8d44-85fabc33492b.png">

1. You should now be in the IBM Cloud Functions web console. The page should have a navigation menu that provides links to all of the top-level features. In this tutorial, you will explore the following feature areas shown in the menu:

    * **Actions**, which are used to create, edit, and manage actions using any supported functional coding language.

    * **Triggers**, which are used to create, edit, and manage triggers that automate the running or firing of your actions using events.

    * **Monitor**, which is used to display information about your action and trigger invocations (such as executions) on your account, including an activity summary and timeline.

1. Create your first action by clicking the **Start Creating** button on the functions home page.

    <img width="1290" alt="3" src="https://user-images.githubusercontent.com/15332386/130031938-1ed92439-97fa-42d0-abd6-513a79951a35.png">

    Then click the **Action** section of the page.

    ![4](https://user-images.githubusercontent.com/15332386/130031946-3ba04586-6c81-4c91-8608-4ef28230754f.png)

1. Enter an action name, such as `hello`, and verify that the runtime dropdown shows the latest default Node.js runtime version (for example, Node.js 10). Now click the **Create** button.

    <img width="960" alt="5" src="https://user-images.githubusercontent.com/15332386/130031948-f48ed2b4-6047-4b07-a88e-7cc6daf5a759.png">

1. In the cloud-based code editor that opens, you can create and modify the function of your action. The editor should be pre-filled with a `Hello World` function written in Node.js:

    ```
    function main(params) {
           return { message: "Hello World" };
       }
    ```

    _Note: If you do not see the same code snippet as the one presented in this step, you can copy and paste it into the code editor, replacing any existing code, and click **Save**. You should then see the **Invoke** button appear for you to use in the next step._

1. Click **Invoke** to test your action directly from your browser.

    <img width="960" alt="6" src="https://user-images.githubusercontent.com/15332386/130032428-b87f7856-4114-4424-9f65-a82f67427f1a.png">

    An **Activations** pane should appear with an activation record caused by your invocation that includes an activation ID, invocation results, and any log entries the function writes (for this tutorial, no log entries should appear).

    <img width="960" alt="7" src="https://user-images.githubusercontent.com/15332386/130032441-391ff6a7-1953-47fb-b37d-3bc2e46a0105.png">

    Now you should see that the result of your invocation is a JSON object with the following `Hello World` message:

    ```
    {
      "message": "Hello World"
    }
    ```

    A unique activation record is logged for every invocation that contains detailed configuration and metric information not shown on this page. Later in this tutorial, you will explore the Monitor dashboard where you can view all account activations over time and access their details.

    _Note: If you navigate away from this window and come back, the activations shown here will be reset._

### 2. Invoke with parameters

The user interface allows named parameters to be declared and passed to functions in JSON object format.

1. Make sure your code window is in edit mode. Update the `hello` action function with the code below and click **Save**:

    ```
    function main(params) {
       return { message: "Hello, " + params.name + " from " + params.place };
    }
    ```

1. This action now requires the input parameters `name` and `place`. To add parameters, click **Invoke with parameters**.

    <img width="600" alt="8" src="https://user-images.githubusercontent.com/15332386/130032453-aae3282b-7c59-4cd1-b4b5-99d510a1c62a.png">

    This will cause the **Change Action Input** dialog box to appear.

1. Add the following JSON data to the **Change Action Input** input area within the dialog box and click **Apply**:

    ```
    {
      "name": "Elrond",
      "place": "Rivendell"
    }
    ```

    <img width="600" alt="9" src="https://user-images.githubusercontent.com/15332386/130032460-fd803f3c-f853-49a4-8432-34a7c00a8333.png">

1. Run the action again using the new input data by clicking **Invoke**. You should receive the following result in the **Activations** pane:

    ```
    {
      "message": "Hello, Elrond from Rivendell"
    }
    ```
  
### 3. Create a web action

Now you will make your `hello` action web-accessible and have IBM Cloud Functions automatically create an HTTP endpoint for it.

1. Select **Actions** from the menu. Then, select your `hello` action.

    <img width="600" alt="15" src="https://user-images.githubusercontent.com/15332386/130032877-df4c94e4-9a85-48f0-b69f-8baadda5076a.png">

1. Update your existing `hello` action with the following code:

   ```
   function main(params) {
       let html = '<html style="color:red"><body><p>' +
       'Hello, ' + params.name + ` from ` + params.place +
       '</p></body></html>'
       return { headers: { "Content-Type": "text/html" },
                body: html };
   }
   ```

    Click **Save**.

    <img width="600" alt="16" src="https://user-images.githubusercontent.com/15332386/130033457-cb65a43a-d73a-4021-a7bb-c2853d64f15b.png">

    When you click **Invoke**, the function now returns your `Hello` message formatted in HTML within the `body` of the HTTP response. Note that you also set the proper `Content-Type` to `text/html` in the HTTP response header.

1. To make your action a web action, select **Endpoints** from the menu. Then, check the **Enable as Web Action** box and click **Save**.

    <img width="600" alt="17" src="https://user-images.githubusercontent.com/15332386/130033463-fa458bd0-f034-4dce-90ba-e84e3a02369b.png">

1. After it is saved, you can open the generated URL in your web browser by clicking on it.

    <img width="1052" alt="18" src="https://user-images.githubusercontent.com/15332386/130033471-83cfd450-79c4-49b6-a0f1-a3756086c166.png">

    Now, your greeting should appear on your web browser page.

    <img width="600" alt="19" src="https://user-images.githubusercontent.com/15332386/130033477-42bdcc14-7ae6-4bcf-8d75-70c028192efa.png">

    However, the greeting shows `undefined` for the values of `name` and `place`. Let's fix that.

1. Append the following query parameters to the URL string in your web browser and resubmit the request by clicking **Enter** on your keyboard.

    ```
    ?name=Frodo&place=Shire
    ```

    The query parameters for `name` and `place` are passed as input parameters into the action and now the message "Hello, Frodo from Shire" should appear on your web browser page.

    <img width="600" alt="20" src="https://user-images.githubusercontent.com/15332386/130033479-21ad1b92-1660-43bb-961c-3ef998d74634.png">
    
    
### 4.Create a Cloudant DB service
1. Go back to IBM Cloud main dashboard and in the search bar type **Cloudand**. You will see **Cloudant-DB** service. Click it.

 <img width="1440" alt="Screen Shot 2021-08-19 at 12 02 28 PM" src="https://user-images.githubusercontent.com/15332386/130034479-99f699e9-58e5-4640-a00f-b6cf2394fa59.png">
 
1. Choose **lite plan** and select the region. Click create.

<img width="1440" alt="Screen Shot 2021-08-19 at 12 02 51 PM" src="https://user-images.githubusercontent.com/15332386/130034774-26bc1ca4-6af2-4466-bab8-ef82efae082d.png">

1. Go back to IBM Cloud main dashboard. You will see the Cloudant service created in the resources summary under **Services and Software**. Click on it.

<img width="1374" alt="Screen Shot 2021-08-19 at 12 03 31 PM" src="https://user-images.githubusercontent.com/15332386/130035470-581512fc-c47c-4c6b-808e-dd19640fd05c.png">

1. Go to **Service Credentials**. Click on **New Credential**. This will generate the `apikey` and `username`. Note them down because we will use them in the next step.
<img width="1440" alt="Screen Shot 2021-08-19 at 12 03 52 PM" src="https://user-images.githubusercontent.com/15332386/130035915-6e198e3e-8c51-49a9-8aa0-7cfda67f1096.png">

### 5. Create a Python Action
1. Just like we created the first Node.js action. We will repeat the same thing and create a new **Action** but this time we will choose Python environment.
<img width="1440" alt="Screen Shot 2021-08-19 at 12 21 25 PM" src="https://user-images.githubusercontent.com/15332386/130034153-7f3ffebf-eedd-4a77-acf8-fb06d030c216.png">

1. Copy this code inside the cloud function
```python
#
#
# main() will be run when you invoke this action
#
# @param Cloud Functions actions accept a single parameter, which must be a JSON object.
#
# @return The output of this action, which must be a JSON object.
#
#
from cloudant.client import Cloudant
from cloudant.error import CloudantException
from cloudant.result import Result, ResultByKey
from datetime import datetime

counter = 0

def main(dict):

    client = Cloudant.iam(dict['username'], dict['apikey'], connect=True)
    global counter
    counter+=1
    
    res = addTime(dict,client)
    return { 'response': res }

def addTime(dict, client):
   
    response= ""
    now = datetime.now()
    current_time = now.strftime("%H:%M:%S")
    myDb = client.create_database("demo-db2")
    if myDb.exists():
        
        data = {
            'counter': counter,
            'time': current_time,
        
            }
    
        # Create a document using the Database API
        doc = myDb.create_document(data)

        # Check that the document exists in the database
        if doc.exists():
            print('SUCCESS!!')
            response= "SUCCESS!!'"
        else:
            response = "Something happened. Please try again"
      
    return response    
    
```

1. Go to **Parameters** and create 2 parameters: `apikey` and `username`. Add the values that you have from the cloudant db created in the previous step (apikey and username).

<img width="1440" alt="Screen Shot 2021-08-19 at 12 01 05 PM" src="https://user-images.githubusercontent.com/15332386/130037602-c889fbd2-2b55-47e3-a00c-8dc2c8ad752e.png">


### 5. Create a trigger

As a FaaS platform, IBM Cloud Functions runs code in response to events. Events can be generated by the following:

* **API calls** fired by standard web or mobile applications, which can be configured to trigger actions. This is what you have been doing so far in the user interface; the invoke button triggered a direct call to your action.

* **Services** that are either part of the IBM Cloud platform or external service providers using triggers.

In these next steps, you will create a trigger to periodically run the python function using the IBM Cloud Functions built-in alarm service.

1. Click **Connected Triggers** in the navigation menu and then click **Add Trigger**.

    <img width="960" alt="10" src="https://user-images.githubusercontent.com/15332386/130032464-dd595ee3-2358-48f9-80f9-c9281712012b.png">
     Now select a **Periodic** as your trigger type.

    ![11](https://user-images.githubusercontent.com/15332386/130032854-7a89fb14-9053-420c-ba6b-19cff6683549.png)

1. In the **Trigger Name** field, type `minute alarm`. Then, within the **Timer Settings** section and **UTC Minutes** pattern, select **Every Minute** from the **Select a pattern** list. Click the **Create & Connect** button to create the trigger and connect it to the `hello` action.

    <img width="884" alt="12" src="https://user-images.githubusercontent.com/15332386/130032862-ee154859-1a81-4cec-86bc-ee5046ade4c8.png">
    
1. Now if you go back to your Cloudant DB service, click on **Launch Dashboard**

<img width="1440" alt="Screen Shot 2021-08-19 at 12 04 21 PM" src="https://user-images.githubusercontent.com/15332386/130038240-9335c6f3-e482-46e3-aa9f-28b9a8980a5c.png">

1. Wait a minute and you will see the database created there. Click on it and inside it you will start seeing the documents that are being created from the cloud function. If you expand every document you see that each one has its own counter value and its time value (these are the data that we are writing for each document and sending it to Cloudant DB). Since the triggers acivate the function every minute, then we will get a new document uploaded to the database every minute. You need to refresh the page to see the new documents.

<img width="1440" alt="Screen Shot 2021-08-19 at 12 51 27 PM" src="https://user-images.githubusercontent.com/15332386/130039148-b4060cad-b494-4a5e-87df-7c26671a28ab.png">

1. Make sure you return to the **Triggers** page and delete the trigger, or it will continue to fire every minute, which is charged against your account tier's compute usage!

    Click the **Delete trigger** icon next to the `minute alarm` to delete it.

   <img width="1568" alt="14" src="https://user-images.githubusercontent.com/15332386/130032875-0fa65606-cdc7-4a49-aabe-80c049962d04.png">

    Select **Delete** on the confirmation dialog box.

    _Note: Alternatively, you can disable the trigger by clicking on its name and unchecking the **Enabled** setting under the Connection column. You would then use the breadcrumb trail to navigate back to the Triggers page._

## Summary

Congratulations! You successfully built and deployed several serverless functions, including web actions that can be invoked from the browser or from microservices (all from inside a browse), and an integration with Cloudant DB.

Now you can try these steps with your own code. Experiment some more with running cloud-native, serverless apps written in Node.js.


## Workshop Resources

- Login/Sign Up for IBM Cloud [Here](https://cloud.ibm.com/registration?utm_medium=Inpersondirected&utm_content=000039JL&utm_term=10010797&utm_id=Aug2021-buildasimpleserverlesshelloworldnodejsappusingcloudfunctions-eventid-60ff224614ed545018eec011-global-devadvgrp-dubai-hybrid-workshop-dubai)
- [Presentation slides]()
- Workshop Replay [Here](https://www.crowdcast.io/e/serverless-hello-world)
- [Survey](https://www.surveygizmo.com/s3/6083679/528d6be4e0fd?uid=60ff224614ed545018eec011)<br/>

- Serverless Q&A [Here](ibm.biz/serverlessQA)
- IBM Cloud Functions[Pricing](https://cloud.ibm.com/functions/learn/pricing)
- IBM Cloud Functions [Limitations](https://cloud.ibm.com/docs/openwhisk?topic=openwhisk-limits)
- Our [Meetup Page](https://www.meetup.com/IBM-Cloud-MEA/)


## Reference Links

https://developer.ibm.com/tutorials/no-infrastructure-just-code-see-the-sim-plicity-of-serverless/
