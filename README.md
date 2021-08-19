# Explore and Build Simple Node.js and Python apps using Cloud Functions

## Workshop Resources

- Login/Sign Up for IBM Cloud [Here](https://cloud.ibm.com/registration?utm_medium=Inpersondirected&utm_content=000039JL&utm_term=10010797&utm_id=Aug2021-buildasimpleserverlesshelloworldnodejsappusingcloudfunctions-eventid-60ff224614ed545018eec011-global-devadvgrp-dubai-hybrid-workshop-dubai)
- [Presentation slides]()
- Workshop Replay [Here](https://www.crowdcast.io/e/serverless-hello-world)
- [Survey](https://www.surveygizmo.com/s3/6083679/528d6be4e0fd?uid=60ff224614ed545018eec011)<br/>

- Servereless Q&A [Here](ibm.biz/serverlessQA)
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

    ![Screen capture of the IBM Cloud dashboard with the Naivgation Menu icon highlighted](images/ibmcloud-dashboard-top-menu.png)

1. Click **Functions** from the menu to access IBM Cloud Functions, the cloud-native development experience on IBM Cloud.

    ![Screen capture of the Navigation Menu with the Functions option highlighted](images/ibmcloud-service-dropdown.png)

1. You should now be in the IBM Cloud Functions web console. The page should have a navigation menu that provides links to all of the top-level features. In this tutorial, you will explore the following feature areas shown in the menu:

    * **Actions**, which are used to create, edit, and manage actions using any supported functional coding language.

    * **Triggers**, which are used to create, edit, and manage triggers that automate the running or firing of your actions using events.

    * **Monitor**, which is used to display information about your action and trigger invocations (such as executions) on your account, including an activity summary and timeline.

1. Create your first action by clicking the **Start Creating** button on the functions home page.

    ![Screen capture of the IBM Cloud Functions home page](images/ibmcloud-functions-start-creating.png)

    Then click the **Action** section of the page.

    ![Screen capture of the Create page](images/ibmcloud-functions-create.png)

1. Enter an action name, such as `hello`, and verify that the runtime dropdown shows the latest default Node.js runtime version (for example, Node.js 10). Now click the **Create** button.

    ![Screen capture of the Create Action page](images/ibmcloud-functions-action-create.png)

1. In the cloud-based code editor that opens, you can create and modify the function of your action. The editor should be pre-filled with a `Hello World` function written in Node.js:

    ```
    function main(params) {
           return { message: "Hello World" };
       }
    ```

    _Note: If you do not see the same code snippet as the one presented in this step, you can copy and paste it into the code editor, replacing any existing code, and click **Save**. You should then see the **Invoke** button appear for you to use in the next step._

1. Click **Invoke** to test your action directly from your browser.

    ![Screen capture of the code editor screen with the Invoke button highlighted](images/ibmcloud-functions-action-invoke.png)

    An **Activations** pane should appear with an activation record caused by your invocation that includes an activation ID, invocation results, and any log entries the function writes (for this tutorial, no log entries should appear).

    ![Screen capture of the action test results that appear in the Activations pane](images/ibmcloud-functions-activation.png)

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

    ![Screen capture of the code editor screen with the Invoke with parameters button highlighted](images/ibmcloud-functions-action-invoke-params.png)

    This will cause the **Change Action Input** dialog box to appear.

1. Add the following JSON data to the **Change Action Input** input area within the dialog box and click **Apply**:

    ```
    {
      "name": "Elrond",
      "place": "Rivendell"
    }
    ```

    ![Screen capture of the Change Action Input dialog box](images/ibmcloud-functions-action-input-dialog.png)

1. Run the action again using the new input data by clicking **Invoke**. You should receive the following result in the **Activations** pane:

    ```
    {
      "message": "Hello, Elrond from Rivendell"
    }
    ```
  
### 3. Create a web action

Now you will make your `hello` action web-accessible and have IBM Cloud Functions automatically create an HTTP endpoint for it.

1. Select **Actions** from the menu. Then, select your `hello` action.

    ![Screen capture of the Actions page with the hello action highlighted](images/ibmcloud-functions-action-select.png)

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

    ![Screen capture of the code editor screen with the Save button highlighted](images/ibmcloud-functions-web-action-create.png)

    When you click **Invoke**, the function now returns your `Hello` message formatted in HTML within the `body` of the HTTP response. Note that you also set the proper `Content-Type` to `text/html` in the HTTP response header.

1. To make your action a web action, select **Endpoints** from the menu. Then, check the **Enable as Web Action** box and click **Save**.

    ![Screen capture of the Endpoints page with a check mark in the Enable as Web Action box and the Save button highlighted](images/ibmcloud-functions-web-action-enable.png)

1. After it is saved, you can open the generated URL in your web browser by clicking on it.

    ![Screen capture of the Web Action portion of the Endpoints page, with the generated URL highlighted](images/ibmcloud-functions-web-action-url.png)

    Now, your greeting should appear on your web browser page.

    ![Screen capture of the greeting, Hello, undefined from undefined, in red text on the web browser page](images/ibmcloud-functions-web-action-output.png)

    However, the greeting shows `undefined` for the values of `name` and `place`. Let's fix that.

1. Append the following query parameters to the URL string in your web browser and resubmit the request by clicking **Enter** on your keyboard.

    ```
    ?name=Frodo&place=Shire
    ```

    The query parameters for `name` and `place` are passed as input parameters into the action and now the message "Hello, Frodo from Shire" should appear on your web browser page.

    ![Screen capture of the greeting, Hello, Frodo from Shirt, in red text on the web browser page](images/ibmcloud-functions-web-action-output-params.png)
  
  
### 4. Create a trigger

As a FaaS platform, IBM Cloud Functions runs code in response to events. Events can be generated by the following:

* **API calls** fired by standard web or mobile applications, which can be configured to trigger actions. This is what you have been doing so far in the user interface; the invoke button triggered a direct call to your action.

* **Services** that are either part of the IBM Cloud platform or external service providers using triggers.

In these next steps, you will create a trigger to periodically run a function using the IBM Cloud Functions built-in alarm service.

1. Update your existing `hello` action with the following sample code and click **Save**:

    ```
    var counter = 0; // global variable
    function main(msg) {
        var date = new Date();
        var time = date.getHours() + ":" + date.getMinutes() + ":" +
        date.getSeconds();
        counter++;
        return { message: "It is " + time + ". This action has been called " + counter + " time(s)." };
    }
    ```

    This action returns the time and the frequency of times invoked. A counter is used as a global variable to maintain the count. Because it is a global variable, it persists across invocations of the same action.

1. Click **Connected Triggers** in the navigation menu and then click **Add Trigger**.

    ![Screen capture of the Connected Triggers page with Add Trigger highlighted](images/ibmcloud-functions-connected-trigger-add.png)

     Now select a **Periodic** as your trigger type.

    ![Screen capture of Connect Trigger page with Periodic option highlighted](images/ibmcloud-functions-connected-trigger-select.png)

1. In the **Trigger Name** field, type `minute alarm`. Then, within the **Timer Settings** section and **UTC Minutes** pattern, select **Every Minute** from the **Select a pattern** list. Click the **Create & Connect** button to create the trigger and connect it to the `hello` action.

    ![Screen capture of the New Trigger Configuration page](images/ibmcloud-functions-trigger-periodic-configure.png)

1. Make sure you return to the **Triggers** page and delete the trigger, or it will continue to fire every minute, which is charged against your account tier's compute usage!

    Click the **Delete trigger** icon next to the `minute alarm` to delete it.

    ![Screen capture of the Triggers page with the Delete trigger icon highlighted next to the minute alarm trigger](images/ibmcloud-functions-trigger-delete.png)

    Select **Delete** on the confirmation dialog box.

    _Note: Alternatively, you can disable the trigger by clicking on its name and unchecking the **Enabled** setting under the Connection column. You would then use the breadcrumb trail to navigate back to the Triggers page._

## Summary

Congratulations! You successfully built and deployed several serverless functions, including web actions that can be invoked from the browser or from microservices - all from inside a browser.

Now you can try these steps with your own code. Experiment some more with running cloud-native, serverless apps written in Node.js.


## Workshop Resources

- Login/Sign Up for IBM Cloud [Here](https://cloud.ibm.com/registration?utm_medium=Inpersondirected&utm_content=000039JL&utm_term=10010797&utm_id=Aug2021-buildasimpleserverlesshelloworldnodejsappusingcloudfunctions-eventid-60ff224614ed545018eec011-global-devadvgrp-dubai-hybrid-workshop-dubai)
- [Presentation slides]()
- Workshop Replay [Here](https://www.crowdcast.io/e/serverless-hello-world)
- [Survey](https://www.surveygizmo.com/s3/6083679/528d6be4e0fd?uid=60ff224614ed545018eec011)<br/>

- Servereless Q&A [Here](ibm.biz/serverlessQA)
- IBM Cloud Functions[Pricing](https://cloud.ibm.com/functions/learn/pricing)
- IBM Cloud Functions [Limitations](https://cloud.ibm.com/docs/openwhisk?topic=openwhisk-limits)
- Our [Meetup Page](https://www.meetup.com/IBM-Cloud-MEA/)


## Reference Links

https://developer.ibm.com/tutorials/no-infrastructure-just-code-see-the-sim-plicity-of-serverless/
