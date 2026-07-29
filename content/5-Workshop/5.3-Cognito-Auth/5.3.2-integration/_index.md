---
title : "Get Credentials & Frontend Integration"
date : 2026-07-27 
weight : 3
chapter : false
pre : " <b> 5.3.2 </b> "
---

#### 5.3.2. Get Credentials & Frontend Integration

After the User Pool is created, you need to extract its IDs to link it with your React application.

1. On the Cognito overview page, copy the **User Pool ID** (e.g., `ap-southeast-2_xxxxxxxxx`).
![Cognito IDs](/images/Screenshot4.png)
2. Navigate to the **App integration** tab, scroll down to *App clients*, and copy the **Client ID**.
![Client IDs](/images/Screenshot5.png)

3. In your React source code (`App.jsx`), install the AWS Amplify library (`npm install aws-amplify @aws-amplify/ui-react`) and configure it using the IDs you just copied:

```javascript
import { Amplify } from 'aws-amplify';
import { withAuthenticator } from '@aws-amplify/ui-react';
import '@aws-amplify/ui-react/styles.css';

// Configure Cognito Authentication
Amplify.configure({
  Auth: {
    Cognito: {
      userPoolId: 'YOUR_USER_POOL_ID_HERE', 
      userPoolClientId: 'YOUR_CLIENT_ID_HERE', 
    }
  }
});












