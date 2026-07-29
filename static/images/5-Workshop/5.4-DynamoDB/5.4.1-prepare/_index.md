---
title : "Why Amazon DynamoDB?"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1 </b> "
---
#### 5.4.1. Why Amazon DynamoDB?
For a real-time chat application, speed and scalability are crucial. We chose DynamoDB over traditional relational databases (like MySQL) because:
* **Serverless & Fully Managed:** There are no servers to provision or manage.
* **Extreme Performance:** It provides consistent, single-digit millisecond response times at any scale, which is perfect for real-time messaging.
* **Flexible Schema:** As a NoSQL database, it easily handles dynamic chat data attributes (e.g., messages with or without images).


