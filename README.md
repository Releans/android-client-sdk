# Getting started

The Releans SDK enables developers to use Releans Services in their code. You can get started in minutes.

## How to Build

The generated code uses a few Gradle dependencies e.g., Jackson, Volley,
and Apache HttpClient. The reference to these dependencies is already
added in the build.gradle file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Android Studio click on ``` Open an Existing Android Project ```.

![Importing SDK into Android Studio - Step 1](https://apidocs.io/illustration/android?step=import1&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

* Browse to locate the folder containing the source code. Select the location of the ReleansAPI gradle project and click ``` Ok ```.

![Importing SDK into Android Studio - Step 2](https://apidocs.io/illustration/android?step=import2&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

* Upon successful import, the project can be built by clicking on ``` Build > Make Project ``` or  pressing ``` Ctrl + F9 ```.

![Importing SDK into Android Studio - Step 3](https://apidocs.io/illustration/android?step=import3&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

## How to Use

The following section explains how to use the ReleansAPI library in a new project.

### 1. Starting a new project 

For starting a new project, click on ``` Create New Android Studio Project ```.

![Add a new project in Android Studio - Step 1](https://apidocs.io/illustration/android?step=createNewProject0&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

Here, configure the new project by adding the name, domain and location of the sample application followed by clicking ``` Next ```.

![Create a new Android Studio Project - Step 2](https://apidocs.io/illustration/android?step=createNewProject1&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

Following this, select the `Phone and Tablet` option as shown in the illustration below and click `Next`.

![Create a new Android Studio Project - Step 3](https://apidocs.io/illustration/android?step=createNewProject2&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

In the following step, choose ``` Empty Activity ``` as the activity type and click ``` Next ```.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject3&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

In this step, provide an ``` Activity Name ``` and ``` Layout Name ``` and click ``` Finish ```.  This would take you to the newly created project.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject4&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

### 2. Add reference of the library project

In order to add a dependency to this sample application, click on the android button shown in the project explorer on the left side as shown in the picture. Click on ``` Project ``` in the drop down that emerges.  

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/android?step=testProject0&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

Right click the sample application in the project explorer and click on ``` New > Module ```  as shown in the picture.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/android?step=testProject1&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

Choose ``` Import Gradle Project ``` and click ``` Next ```.

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/android?step=testProject2&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

Click on ``` Finish ``` which would take you back to the sample application with the refernced SDK. 

![Adding dependency to the client library - Step 4](https://apidocs.io/illustration/android?step=testProject3&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

In the following step first navigate to the ``` SampleApplication > settings.gradle ``` file and add the line
```include ':ReleansAPILib'```

Then navigate to the ``` SampleApplication >  app > build.gradle ``` file and add the following line 
```implementation project(path: ':ReleansAPILib')```
to the dependencies section as shown in the illustration below. Also add the following packagingOptions.

packagingOptions
    exclude 'META-INF/LICENSE'
    exclude 'META-INF/NOTICE'
    exclude 'META-INF/DEPENDENCIES'
}

![Adding dependency to the client library - Step 5](https://apidocs.io/illustration/android?step=testProject4&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

Finally, press ``` Sync Now ``` in the warning visible as shown in the picture below.

![Adding dependency to the client library - Step 6](https://apidocs.io/illustration/android?step=testProject5&workspaceFolder=Releans%20API&workspaceName=ReleansAPI&projectName=ReleansAPILib&rootNamespace=com.releans.platform)

### 3. Write sample code

Once the ``` SampleApplication ``` is created, a file named ``` SampleApplication > app > src > main > java > MainActivity ``` will be visible in the *Project Explorer* with an ``` onCreate ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

## How to Test

The generated code and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Android Studio, for running the tests do the following:

1. Right click on *SampleApplication > ReleansAPILib > androidTest > java)* from the project explorer.
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

com.releans.platform.Configuration.initialize(appContext);
ReleansAPIClient client = new ReleansAPIClient(oAuthAccessToken);
```


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [MessageController](#message_controller)
* [SenderController](#sender_controller)
* [BalanceController](#balance_controller)

## <a name="message_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.releans.platform.controllers.MessageController") MessageController

### Get singleton instance

The singleton instance of the ``` MessageController ``` class can be accessed from the API Client.

```java
MessageController message = client.getMessage();
```

### <a name="get_all_messages_async"></a>![Method: ](https://apidocs.io/img/method.png "com.releans.platform.controllers.MessageController.getAllMessagesAsync") getAllMessagesAsync

> List all messages sent by the account.


```java
void getAllMessagesAsync(
        final String accept,
        final APICallBack<DynamicResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| accept |  ``` Required ```  | TODO: Add a parameter description |


#### Example Usage

```java
String accept = "*/*";
// Invoking the API call with sample inputs
message.getAllMessagesAsync(accept, new APICallBack<DynamicResponse>() {
    public void onSuccess(HttpContext context, DynamicResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="get_view_message_async"></a>![Method: ](https://apidocs.io/img/method.png "com.releans.platform.controllers.MessageController.getViewMessageAsync") getViewMessageAsync

> Return the details of the message.


```java
void getViewMessageAsync(
        final String id,
        final String accept,
        final APICallBack<DynamicResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  | TODO: Add a parameter description |
| accept |  ``` Required ```  | TODO: Add a parameter description |


#### Example Usage

```java
String id = "id";
String accept = "*/*";
// Invoking the API call with sample inputs
message.getViewMessageAsync(id, accept, new APICallBack<DynamicResponse>() {
    public void onSuccess(HttpContext context, DynamicResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="create_send_sms_message_async"></a>![Method: ](https://apidocs.io/img/method.png "com.releans.platform.controllers.MessageController.createSendSMSMessageAsync") createSendSMSMessageAsync

> Send a single message.


```java
void createSendSMSMessageAsync(
        final String accept,
        final String senderId,
        final String mobileNumber,
        final String message,
        final APICallBack<DynamicResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| accept |  ``` Required ```  | TODO: Add a parameter description |
| senderId |  ``` Required ```  | Sender id to send the message from. |
| mobileNumber |  ``` Required ```  | The mobile number supposed to receive the message. |
| message |  ``` Required ```  | Message text. |


#### Example Usage

```java
String accept = "Accept";
String senderId = "senderId";
String mobileNumber = "mobileNumber";
String message = "message";
// Invoking the API call with sample inputs
message.createSendSMSMessageAsync(accept, senderId, mobileNumber, message, new APICallBack<DynamicResponse>() {
    public void onSuccess(HttpContext context, DynamicResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


[Back to List of Controllers](#list_of_controllers)

## <a name="sender_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.releans.platform.controllers.SenderController") SenderController

### Get singleton instance

The singleton instance of the ``` SenderController ``` class can be accessed from the API Client.

```java
SenderController sender = client.getSender();
```

### <a name="get_sender_name_details_async"></a>![Method: ](https://apidocs.io/img/method.png "com.releans.platform.controllers.SenderController.getSenderNameDetailsAsync") getSenderNameDetailsAsync

> Return the details of the sender name.


```java
void getSenderNameDetailsAsync(
        final String id,
        final String accept,
        final APICallBack<DynamicResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  | TODO: Add a parameter description |
| accept |  ``` Required ```  | TODO: Add a parameter description |


#### Example Usage

```java
String id = "sender-id";
String accept = "*/*";
// Invoking the API call with sample inputs
sender.getSenderNameDetailsAsync(id, accept, new APICallBack<DynamicResponse>() {
    public void onSuccess(HttpContext context, DynamicResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="create_sender_name_async"></a>![Method: ](https://apidocs.io/img/method.png "com.releans.platform.controllers.SenderController.createSenderNameAsync") createSenderNameAsync

> Create a new sender id to send messages using it


```java
void createSenderNameAsync(
        final String accept,
        final String contentType,
        final String body,
        final APICallBack<Response200> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| accept |  ``` Required ```  | TODO: Add a parameter description |
| contentType |  ``` Required ```  | TODO: Add a parameter description |
| body |  ``` Required ```  | TODO: Add a parameter description |


#### Example Usage

```java
String accept = "text/plain";
String contentType = "text/plain";
String body = "Your sender name";
// Invoking the API call with sample inputs
sender.createSenderNameAsync(accept, contentType, body, new APICallBack<Response200>() {
    public void onSuccess(HttpContext context, Response200 response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


### <a name="get_all_senders_async"></a>![Method: ](https://apidocs.io/img/method.png "com.releans.platform.controllers.SenderController.getAllSendersAsync") getAllSendersAsync

> List all senders names associated with the account


```java
void getAllSendersAsync(
        final String accept,
        final APICallBack<List<Response2001>> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| accept |  ``` Required ```  | TODO: Add a parameter description |


#### Example Usage

```java
String accept = "*/*";
// Invoking the API call with sample inputs
sender.getAllSendersAsync(accept, new APICallBack<List<Response2001>>() {
    public void onSuccess(HttpContext context, List<Response2001> response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


[Back to List of Controllers](#list_of_controllers)

## <a name="balance_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.releans.platform.controllers.BalanceController") BalanceController

### Get singleton instance

The singleton instance of the ``` BalanceController ``` class can be accessed from the API Client.

```java
BalanceController balance = client.getBalance();
```

### <a name="get_balance_async"></a>![Method: ](https://apidocs.io/img/method.png "com.releans.platform.controllers.BalanceController.getBalanceAsync") getBalanceAsync

> Get your available balance


```java
void getBalanceAsync(
        final String accept,
        final APICallBack<Response2002> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| accept |  ``` Required ```  | TODO: Add a parameter description |


#### Example Usage

```java
String accept = "text/plain";
// Invoking the API call with sample inputs
balance.getBalanceAsync(accept, new APICallBack<Response2002>() {
    public void onSuccess(HttpContext context, Response2002 response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```


[Back to List of Controllers](#list_of_controllers)



