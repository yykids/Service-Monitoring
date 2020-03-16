## Management > Service Monitoring > API Guide

### Basic information
```
API Endpoint: https://api-service-monitoring.cloud.toast.com
```
## Single Batch Monitoring 

### Data Transfer
-  Transfers data which must be verified by the batch monitoring server.
- The JSON type data can be sent according to the verification information entered for batch monitoring. When verification of batch monitoring fails, it is registered as a failure.

[URL]
```
POST /v1.0/monitoring/batchmon/appkey/{appKey}/scenarios/{scenarioId}
Content-Type: application/json
```

[Path Variables]

| Value |	Type | Required? |	Description |
|---|---|---|--|
| appKey | String | Required | Service App Key(You can view this on Manage Service tab) |
| scenarioId | String | Required | Service ID |

[Request Body]
```json
{
    "issueDescription": "This is test message."
}
```


#### Response
```json
{
    "header": {
        "isSuccessful": true,
        "resultCode": 0,
        "resultMessage": "SUCCESS"
    },
    "body": {
        "pk": {
            "serviceId": "d781dafc-2d5e-3d11-a87e-529b0868ea4f",
            "requestId": "3f136280-9d6a-11e9-83b4-ff39d67ddecf"
        },
        "scenarioId": "b00699c0-96f4-11e9-a68b-a7aaea9ae346",
        "ipaddr": "192.168.0.1",
        "requestTime": "2099-12-31T00:00:00.000",
        "requestData": {
            "body": "{\"issueDescription\": \"This is test message.\"}"
        },
        "serviceCode": 0,
        "status": "beforeValidation"
    }
}
```

| Value | Type | Description |
|---|---|---|
| header.isSuccessful | boolean | Success or Fail |
| header.resultCode | Integer | Fail code(0 is normal) |
| header.resultMessage | String | Fail message |
| body.pk.serviceId | String | Unique ID of the service |
| body.pk.requestId | String | Unique ID of the request |
| body.scenarioId | String | Unique ID of the scenario |
| body.requestData.body | Object | Request data |
| body.ipaddr | String | IP address of the requestor |
| body.requestTime | String | Request time (ISO 8601 format) |
| body.serviceCode | Integer | Unique code of the service |
| body.status | String | Request status |

## Multiple Batch Monitoring 
- Verify multiple services and scenarios, with a single request.  
- Not verify, when normal appkey or scenario ID exist. 

### Data Transfer 
- Send data in need of verification to bach monitoring server. 
- Send JSON-type data according to verification information entered at batch monitoring; if verification fails for batch monitoring, register as failure. 

[URL]
```http
POST /v1.0/monitoring/batchmon
Content-Type: application/json
```

[Request Body]
```json
{
    "target" : [
        {
            "appkey" : "81713f1cc96b4eae834f7535ec4fae7a",
            "scenarioIdList" : [
                "12962600-5c39-11ea-bd8f-0bbd7856015c"
            ]
        },
        {
            "appkey" : "2aac90b8f3c64fcb8083d1ed0218192c",
            "scenarioIdList" : [
                "1b648d20-5c39-11ea-bd8f-0bbd7856015c"
            ]
        }
    ],
    "data" : "{\"key\": \"value\"}"
}
```


#### Response
```json
{
    "body": [
        {
            "ipaddr": "127.0.0.1",
            "pk": {
                "requestId": "1958be80-5c3b-11ea-bd8f-0bbd7856015c",
                "serviceId": "128248e0-ff3b-34cd-be87-2b5bd173febb"
            },
            "requestData": {
                "body": "{\"key\": \"value\"}"
            },
            "requestTime": "2099-12-31T00:00:00.000",
            "scenarioId": "12962600-5c39-11ea-bd8f-0bbd7856015c",
            "serviceCode": 0
        },
        {
            "ipaddr": "127.0.0.1",
            "pk": {
                "requestId": "1959a8e0-5c3b-11ea-bd8f-0bbd7856015c",
                "serviceId": "1ab4e137-a158-346b-bacc-7e0c76466ac0"
            },
            "requestData": {
                "body": "{\"key\": \"value\"}"
            },
            "requestTime": "2099-12-31T00:00:00.000",
            "scenarioId": "1b648d20-5c39-11ea-bd8f-0bbd7856015c",
            "serviceCode": 1
        }
    ],
    "header": {
        "isSuccessful": true,
        "resultCode": 0,
        "resultMessage": "SUCCESS"
    }
}
```
| Value | Type | Description |
|---|---|---|
| header.isSuccessful | Boolean | Successful or Not |
| header.resultCode | Integer | Failure Code (0 is normal) |
| header.resultMessage | String | Failure Message |
| body.pk.serviceId | String | Original Service ID |
| body.pk.requestId | String | Original Request ID |
| body.scenarioId | String | Original Scenario ID |
| body.requestData.body | Object | Request Data |
| body.ipaddr | String | IP Address of Requestor |
| body.requestTime | String | Request Time (ISO 8601 format) |
| body.serviceCode | Integer | Original Service Code |
