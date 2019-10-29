## Management > Service Monitoring > API Guide

### Basic information
```
API Endpoint: https://api-service-monitoring.cloud.toast.com
```

## Batch Monitoring

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
| body.pk.requstId | String | Unique ID of the request |
| body.scenarioId | String | Unique ID of the scenario |
| body.requestData.body | Object | Request data |
| body.ipaddr | String | IP address of the requestor |
| body.requestTime | String | Request time (ISO 8601 format) |
| body.serviceCode | Integer | Unique code of the service |
| body.status | String | Request status |
