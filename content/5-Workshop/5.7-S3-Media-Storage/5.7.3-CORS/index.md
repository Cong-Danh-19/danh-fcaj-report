---
title : "Configure CORS"
date : 2026-07-27
weight : 7
chapter : false
pre : " <b> 5.7.3 </b> "
---

#### 5.7.3. Configure CORS (Cross-Origin Resource Sharing)

Without CORS, the browser will block the frontend from uploading images directly
to S3.

1.  Still in the Permissions tab, scroll to the bottom to find Cross-origin
    resource sharing (CORS).
![DynamoDB Tables](images/Screenshot9.PNG)

2.  Click Edit and paste the following JSON configuration:

```json
[
    {
        "AllowedHeaders": ["*"],
        "AllowedMethods": ["PUT", "GET"],
        "AllowedOrigins": ["*"],
        "ExposeHeaders": []
    }
]
```
![DynamoDB Tables](images/Screenshot10.PNG)

3.  Click Save changes.
![DynamoDB Tables](images/Screenshot11.PNG)

