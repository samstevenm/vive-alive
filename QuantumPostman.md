# Api Webhook Validation Function

## About

### Quantum Api Alpha Postman Collection
Postman collection that contains all of the requests currently supported (Documented) in the Quantum API Partner Technical documentation.

### Api Webhook Validation Function
This project/Visual Studio solution was created to manage the code of an Azure Function that can be leveraged to test the Quantum (Gulliver Server) API. This funciton is meant to specifically targeted to test the Webhook/Push functionality where the API will push updates (Area Occupancy Status) to a partner's HTTP Webhook endpoint.

## Quantum Api Alpha Postman Collection

### Collection Details
The collection is a basic Postman collection that contains requests supported by the Quantum API. It currently uses the following collection variablies:
1. Api_Url - This variable is used by all collection requests to determine what endpoint to send a request to. For example, the Quantum API alpha instance is hosted on the Lutron blue network at https://quantumapi.intra.lutron.com/api/v1/leap. If you are testing with a different API, replace quantumapi.intra.lutron.com with the hostname of that instance.
2. Device_Key - This variable is used by all collection requests as the device key configured for a single "device" to communicate to the API.
3. Api_Key - This variable is used by all collections as the partner API key. If you are testing a specific 3rd party partner's key, this value can be updated. The Lutron Development API key is 560D2FDDA9E843CCAFCF39BDCE82E4C2, note the API must be running in development (non-production) mode for this API key to work.
4. Area_Href - This variable is used for the Get Area Definition and Get Area Status Requests. Replace this with the area href: /area/{Area_ID}.
5. Zone_Href - This variable is used for the Get Zone Definion and Get Zone Satus Requests. Replace this with the zone href: /zone/{Zone_ID}.

### Supported Requests
System Ping

Get Root Area

Get Area Definition

Get Area Status

Get Zone Definition

Get Zone Status

### How to Update Variables in Postman
1. Download QuantumApiAlphaPostmanCollection.postman_collection.json.
2. Open Postman application (https://www.postman.com/downloads/)
3. Import postman colleciton downloaded in step 1.
    File -> Import
    In File tab -> Upload Files
    Select the postman collection downloaded
    Click Import.
4. The collection should show up on the left side of a screen as a folder. Expand to see the individual requests.
5. Hover over the collection name/folder, and click the 3 dots that appear.
6. Click edit.
7. Open Variables tab.
8. Fill in the Current Value column with the desired variable values.
9. Click update.
10. In the main screen, you can now select a request and click send.


### Variable Values for Alpha and Demo Sites

#### CB5 4th Floor Alpha Site
Api_Url: https://quantumapi.intra.lutron.com/api/v1/leap
Device_Key: 1201f70a-105a-4350-9bac-5e0b1874cb41
Api_Key: 560D2FDDA9E843CCAFCF39BDCE82E4C2
Area_Href:
Zone_Href:

#### CB5 2nd Floor Alpha Site
Api_Url: https://quantumapi.intra.lutron.com/api/v1/leap
Device_Key: bf7bd8a8-7016-45a3-9ccb-33e09155b364
Api_Key: 560D2FDDA9E843CCAFCF39BDCE82E4C2
Area_Href:
Zone_Href:

#### Partner Integration Sandbox (LS1496)
Api_Url: https://engineeringwebdemo01.lutron.com/api/v1/leap
Device_Key: c7cabce5-41fc-4b95-a7a7-022893aac43a
Api_Key: 560D2FDDA9E843CCAFCF39BDCE82E4C2
Area_Href: /area/706
Zone_Href: /zone/817

## Api Webhook Validation Function

### Deploying to Azure Alpha Instance
Download Azure Publish Profile
1. Go to https://portal.azure.com and login with your Lutron account.
2. Navigate to All Resources
3. Find and navigate to the ApiWebhookValidationFunction App Service
* Subscription == Visual Studio Professional
* Type == App Service
* Resource Group == Gulliver_Quantum_API
4. Get Publish Profile

Publish to Azure from Visual Studio
1. Open the ApiWebhookValidationFuntion.sln in Visual Studio
2. On the Menu Bar go to Build > Publish to Azure...
3. Pick the ApiWebhookValidationFunction from the list of Azure App Services and click Publish.

### Local Deployment
#### Using Visual Studio
An Azure Funtion can be tested on a Windows PC or Mac OS machine with Visual Studio installed, simply by running/debugging the application from Visual Studio. 

https://docs.microsoft.com/en-us/azure/azure-functions/functions-develop-vs

#### Work with Azure Function Core Tools
https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=windows%2Ccsharp%2Cbash