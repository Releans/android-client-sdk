# Getting started

The Releans SDK enables developers to use Releans Services in their code. You can get started in minutes.

## Create Releans Account

First, [sign up for a Releans account](https://platform.releans.com/site/signup) if you don't already have one, and make a note of your API key on the dashboard API page.

## How to Build

The Releans sdk uses a few Gradle dependencies e.g., Jackson, Volley,
and Apache HttpClient. The reference to these dependencies is already
added in the build.gradle file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Android Studio click on ``` Open an Existing Android Project ```.

![Importing SDK into Android Studio - Step 1](https://apidocs.io/illustration/android?step=import1&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

* Browse to locate the folder containing the source code. Select the location of the Releans gradle project and click ``` Ok ```.

![Importing SDK into Android Studio - Step 2](https://apidocs.io/illustration/android?step=import2&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

* Upon successful import, the project can be built by clicking on ``` Build > Make Project ``` or  pressing ``` Ctrl + F9 ```.

![Importing SDK into Android Studio - Step 3](https://apidocs.io/illustration/android?step=import3&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

## How to Use

The following section explains how to use the Releans library in a new project.

### 1. Starting a new project 

For starting a new project, click on ``` Create New Android Studio Project ```.

![Add a new project in Android Studio - Step 1](https://apidocs.io/illustration/android?step=createNewProject0&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

Here, configure the new project by adding the name, domain and location of the sample application followed by clicking ``` Next ```.

![Create a new Android Studio Project - Step 2](https://apidocs.io/illustration/android?step=createNewProject1&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

Following this, select the `Phone and Tablet` option as shown in the illustration below and click `Next`.

![Create a new Android Studio Project - Step 3](https://apidocs.io/illustration/android?step=createNewProject2&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

In the following step, choose ``` Empty Activity ``` as the activity type and click ``` Next ```.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject3&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

In this step, provide an ``` Activity Name ``` and ``` Layout Name ``` and click ``` Finish ```.  This would take you to the newly created project.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject4&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

### 2. Add reference of the library project

In order to add a dependency to this sample application, click on the android button shown in the project explorer on the left side as shown in the picture. Click on ``` Project ``` in the drop down that emerges.  

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/android?step=testProject0&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

Right click the sample application in the project explorer and click on ``` New > Module ```  as shown in the picture.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/android?step=testProject1&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

Choose ``` Import Gradle Project ``` and click ``` Next ```.

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/android?step=testProject2&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

Click on ``` Finish ``` which would take you back to the sample application with the refernced SDK. 

![Adding dependency to the client library - Step 4](https://apidocs.io/illustration/android?step=testProject3&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

In the following step first navigate to the ``` SampleApplication > settings.gradle ``` file and add the line
```include ':Releans'```

Then navigate to the ``` SampleApplication >  app > build.gradle ``` file and add the following line 
```implementation project(path: ':Releans')```
to the dependencies section as shown in the illustration below. Also add the following packagingOptions.

packagingOptions
    exclude 'META-INF/LICENSE'
    exclude 'META-INF/NOTICE'
    exclude 'META-INF/DEPENDENCIES'
}

![Adding dependency to the client library - Step 5](https://apidocs.io/illustration/android?step=testProject4&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

Finally, press ``` Sync Now ``` in the warning visible as shown in the picture below.

![Adding dependency to the client library - Step 6](https://apidocs.io/illustration/android?step=testProject5&workspaceFolder=Releans&workspaceName=Releans&projectName=Releans&rootNamespace=Releans)

### 3. Write sample code

Once the ``` SampleApplication ``` is created, a file named ``` SampleApplication > app > src > main > java > MainActivity ``` will be visible in the *Project Explorer* with an ``` onCreate ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

## How to Test

The Releans sdk and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Android Studio, for running the tests do the following:

1. Right click on *SampleApplication > Releans > androidTest > java)* from the project explorer.
2. Select "Run All Tests" or use "Ctrl + Shift + F10" to run the Tests.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthAccessToken | OAuth 2.0 Access Token |



API client can be initialized as following. The `appContext` being passed is the Android application [`Context`](https://developer.android.com/reference/android/content/Context.html).

```java
// Configuration parameters and credentials
String oAuthAccessToken = "oAuthAccessToken"; // OAuth 2.0 Access Token

Releans.Configuration.initialize(appContext);
ReleansClient client = new ReleansClient(oAuthAccessToken);
```


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [MessageController](#message_controller)
* [SenderController](#sender_controller)
* [BalanceController](#balance_controller)

## <a name="message_controller"></a>![Class: ](https://apidocs.io/img/class.png "Releans.controllers.MessageController") MessageController

### Get singleton instance

The singleton instance of the ``` MessageController ``` class can be accessed from the API Client.

```java
MessageController message = client.getMessage();
```

### <a name="get_all_messages_async"></a>![Method: ](https://apidocs.io/img/method.png "Releans.controllers.MessageController.getAllMessagesAsync") getAllMessagesAsync

> List all messages sent by the account.


```java
void getAllMessagesAsync(final APICallBack<DynamicResponse> callBack)
```

#### Example Usage

```java
// Invoking the API call with sample inputs
message.getAllMessagesAsync(new APICallBack<DynamicResponse>() {
    public void onSuccess(HttpContext context, DynamicResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="get_price_of_message_async"></a>![Method: ](https://apidocs.io/img/method.png "Releans.controllers.MessageController.getPriceOfMessageAsync") getPriceOfMessageAsync

> Return cost of sending a message to the number.


```java
void getPriceOfMessageAsync(
        final String mobileNumber,
        final APICallBack<String> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mobileNumber |  ``` Required ```  | Mobile number you want to know the price of sending a message. |


#### Example Usage

```java
String mobileNumber = "mobileNumber";
// Invoking the API call with sample inputs
message.getPriceOfMessageAsync(mobileNumber, new APICallBack<String>() {
    public void onSuccess(HttpContext context, String response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="get_view_message_async"></a>![Method: ](https://apidocs.io/img/method.png "Releans.controllers.MessageController.getViewMessageAsync") getViewMessageAsync

> Return the details of the message.


```java
void getViewMessageAsync(
        final String id,
        final APICallBack<DynamicResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  ``` DefaultValue ```  | Id of the message you need to return its details. |


#### Example Usage

```java
String id = "id";
// Invoking the API call with sample inputs
message.getViewMessageAsync(id, new APICallBack<DynamicResponse>() {
    public void onSuccess(HttpContext context, DynamicResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="create_send_sms_message_async"></a>![Method: ](https://apidocs.io/img/method.png "Releans.controllers.MessageController.createSendSMSMessageAsync") createSendSMSMessageAsync

> Send a single message.


```java
void createSendSMSMessageAsync(
        final String senderId,
        final String mobileNumber,
        final String message,
        final APICallBack<String> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| senderId |  ``` Required ```  ``` DefaultValue ```  | Sender id to send the message from. |
| mobileNumber |  ``` Required ```  ``` DefaultValue ```  | The mobile number supposed to receive the message. |
| message |  ``` Required ```  ``` DefaultValue ```  | Message text. |


#### Example Usage

```java
String senderId = "sender-id";
String mobileNumber = "mobile-number";
String message = "message";
// Invoking the API call with sample inputs
message.createSendSMSMessageAsync(senderId, mobileNumber, message, new APICallBack<String>() {
    public void onSuccess(HttpContext context, String response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


[Back to List of Controllers](#list_of_controllers)

## <a name="sender_controller"></a>![Class: ](https://apidocs.io/img/class.png "Releans.controllers.SenderController") SenderController

### Get singleton instance

The singleton instance of the ``` SenderController ``` class can be accessed from the API Client.

```java
SenderController sender = client.getSender();
```

### <a name="get_sender_name_details_async"></a>![Method: ](https://apidocs.io/img/method.png "Releans.controllers.SenderController.getSenderNameDetailsAsync") getSenderNameDetailsAsync

> Return the details of the sender name.


```java
void getSenderNameDetailsAsync(
        final String id,
        final APICallBack<DynamicResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  ``` DefaultValue ```  | The sender id you want its details |


#### Example Usage

```java
String id = "sender-id";
// Invoking the API call with sample inputs
sender.getSenderNameDetailsAsync(id, new APICallBack<DynamicResponse>() {
    public void onSuccess(HttpContext context, DynamicResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="create_sender_name_async"></a>![Method: ](https://apidocs.io/img/method.png "Releans.controllers.SenderController.createSenderNameAsync") createSenderNameAsync

> Create a new sender id to send messages using it


```java
void createSenderNameAsync(
        final String senderName,
        final APICallBack<String> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| senderName |  ``` Required ```  ``` DefaultValue ```  | Name you want to register as Sender Name |


#### Example Usage

```java
String senderName = "Your sender name";
// Invoking the API call with sample inputs
sender.createSenderNameAsync(senderName, new APICallBack<String>() {
    public void onSuccess(HttpContext context, String response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="get_all_senders_async"></a>![Method: ](https://apidocs.io/img/method.png "Releans.controllers.SenderController.getAllSendersAsync") getAllSendersAsync

> List all senders names associated with the account


```java
void getAllSendersAsync(final APICallBack<DynamicResponse> callBack)
```

#### Example Usage

```java
// Invoking the API call with sample inputs
sender.getAllSendersAsync(new APICallBack<DynamicResponse>() {
    public void onSuccess(HttpContext context, DynamicResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


[Back to List of Controllers](#list_of_controllers)

## <a name="balance_controller"></a>![Class: ](https://apidocs.io/img/class.png "Releans.controllers.BalanceController") BalanceController

### Get singleton instance

The singleton instance of the ``` BalanceController ``` class can be accessed from the API Client.

```java
BalanceController balance = client.getBalance();
```

### <a name="get_balance_async"></a>![Method: ](https://apidocs.io/img/method.png "Releans.controllers.BalanceController.getBalanceAsync") getBalanceAsync

> Get your available balance


```java
void getBalanceAsync(final APICallBack<String> callBack)
```

#### Example Usage

```java
// Invoking the API call with sample inputs
balance.getBalanceAsync(new APICallBack<String>() {
    public void onSuccess(HttpContext context, String response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


[Back to List of Controllers](#list_of_controllers)



