# Sports Alert System: NBA Game Notifications

## **Introduction**
This notification system delivers real-time NBA game scores through SMS and email channels. The solution integrates AWS cloud services with professional sports data APIs to create a robust, scalable alerting platform.

## **Features**
The system provides comprehensive game-day coverage through:
- Automated delivery of live NBA score updates
- Multi-channel notifications via SMS and email communication
- Scheduled updates powered by Amazon EventBridge
- Enterprise-level security implementation with least-privilege access controls

## **Technologies**
- **Cloud Provider**: AWS
- **Core Services**: SNS, Lambda, EventBridge
- **External API**: NBA Game API (SportsData.io)
- **Programming Language**: Python 3.x
- **IAM Security**:
  - Least privilege policies for Lambda, SNS, and EventBridge.


## **Solution Architecture**
![NBA Architecture Diagram](./solution-architecture.drawio.svg)
The system employs a serverless architecture leveraging:
- AWS Simple Notification Service (SNS) for message distribution
- AWS Lambda with Python for serverless processing
- Amazon EventBridge for automated scheduling
- External NBA data feeds via SportsData.io

## **Implementation Guide**

### System Configuration
1. **Establish the notification infrastructure:**
   ```bash
   git clone https://github.com/MwangangiBrian/court-side-notifications.git
   cd game-day-notifications
   ```

2. **Configure the SNS messaging service:**
   - Create a standard SNS topic through AWS Console
   - Document the topic ARN for later reference
   - Enable email and SMS subscriptions as needed

3. **Implement security policies:**
   - Deploy the provided IAM policies for SNS, Lambda, and EventBridge
   - Establish the Lambda execution role with appropriate permissions
   - Apply least-privilege access controls

4. **Deploy the notification service:**
   - Create a Python-based Lambda function
   - Configure environment variables for API access        
    Under the Environment Variables section, add the following:
        - NBA_API_KEY: your NBA API key.
        - SNS_TOPIC_ARN: the ARN of the SNS topic created earlier.
   - Implement the event trigger schedule
   - Validate the deployment through testing

### **File Structure**
```
game-day-notifications/
├── src/
│   └── gd_notifications.py
├── policies/
│   ├── gb_sns_policy.json
└── README.md
```

## **Development Insights**
The project demonstrates several key architectural principles:
- Cloud-native notification systems development
- Implementation of secure IAM frameworks
- Integration of external data providers
- Automated workflow orchestration

## **Strategic Roadmap**
Future enhancements under consideration include:
- NFL score integration for expanded sports coverage
- User preference management through DynamoDB
- Web-based administration interface
- Enhanced personalization features

## **Verification Process**
To validate the deployment:
1. Execute a Lambda test event
2. Monitor CloudWatch logs for operational status
3. Confirm receipt of test notifications
4. Validate scheduled trigger functionality