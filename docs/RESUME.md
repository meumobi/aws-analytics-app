# Data Analytics w/ AWS Pinpoint

The aim of this project is to discover/test Data Analytics solution of AWS. I'm familiar w/ Google Analytics, but I didn't find a similar solution (out-of-box) on AWS-world. But it seems I can reach same level of insights by combining different AWS modules as illustrated below:

| ![Data stream from Kinesis Data Streams to QuickSight](https://miro.medium.com/max/1356/1*ErLceGXkOFoeSoWOVXQoeQ.png) |
| :-------------------------------------------------------------------------------------------------------------------: |
|                                  Data stream from Kinesis Data Streams to QuickSight                                  |

For testing purpose I've created a sample SPA (Single Page Application) project with authentication and navigation (master-detail) to test [built-in auto-track](https://docs.amplify.aws/lib/analytics/autotrack/q/platform/js/#page-view-tracking) sessions, page views, page events and auth.

and set up a data stream from Kinesis Data Streams to QuickSight

The Amazon Kinesis Firehose analytics provider allows you to send analytics data to an Amazon Kinesis Firehose stream for reliably storing data.

Amplify supports [Amazon Kinesis Data Streams](https://aws.amazon.com/kinesis/data-streams/) to deliver logs from the front-end to QuickSight.

1. **Kinesis Data Firehose delivery stream** delivers data to S3 through Kinesis Data Stream.
1. **AWS Glue** runs a crawler that gathers data from the S3 bucket.
1. Then you are ready to query the data from S3 through AWS Glue by **Athena**.
1. Visualise data on **QuickSight**.

[Tracking open and click events in email](https://docs.aws.amazon.com/pinpoint/latest/userguide/channels-email-open-click-tracking.html)
Amazon Pinpoint automatically tracks how many of your emails were opened or clicked by their recipients.

userAttributes: add user attributes to track data that applies to an individual and doesn't vary based on which device the person is using

- [Collect analytics](./COLLECT_ANALYTICS.md)
- [Analytics dashboard](./ANALYTICS_DASHBOARD.md)
- [Custom analytics](./CUSTOM_ANALYTICS.md)
- [Email campaign](./EMAIL_CAMPAIGN.md)

## AWS Pinpoint

You can use [Amazon Pinpoint](https://docs.aws.amazon.com/pinpoint/latest/developerguide/welcome.html) to send push notifications, emails, SMS text messages, or voice messages.

Major features of Amazon Pinpoint:

- **Define audience segments**
  - Reach the right audience for your messages by defining audience segments. A segment designates which users receive the messages that are sent from a campaign. You can define dynamic segments based on data that's reported by your application, such as operating system or mobile device type. You can also import static segments that you define by using another service or application.
- **Engage your audience with messaging campaigns**
  - Engage your audience by creating a messaging campaign. A campaign sends tailored messages on a schedule that you define. You can create campaigns that send mobile push, email, or SMS messages.
- **Send transactional messages**
  - Keep your customers informed by sending transactional mobile push and SMS messages—such as new account activation messages, order confirmations, and password reset notifications— directly to specific users. You can send transactional messages by using the Amazon Pinpoint REST API.
- **Analyze user behavior**
  - Gain insights about your audience and the effectiveness of your campaigns by using the analytics that Amazon Pinpoint provides. You can view trends about your users' level of engagement, purchase activity, demographics, and more. You can also monitor your message traffic by viewing metrics such as the total number of messages that were sent or opened for a campaign or application.

### Registering endpoints

The endpoint represents the device that the user starts the session with. It includes attributes that describe the device, and it can also include custom attributes that you define.

You can assign a single user ID to multiple endpoints. A user ID represents a single user, while each endpoint that is assigned the user ID represents one of the user's devices.

If someone uses your app on multiple devices, or if that person can be messaged at multiple addresses, you can assign the same user ID to multiple endpoints. In this case, Amazon Pinpoint synchronizes user attributes across the endpoints. So, if you add a user attribute to one endpoint, Amazon Pinpoint adds that attribute to each endpoint that includes the same user ID.

### Reporting events

Call the Amazon Pinpoint API to report the following types of events:

- Session events
  - Indicate when and how often users open and close your app.
- Custom events
  - Are nonstandard events that you define by assigning a custom event type. You can add custom attributes and metrics to a custom event.
- Authentication events
  - Indicate how frequently users authenticate with your application.

After you integrate your application (app) with Amazon Pinpoint, Amazon Pinpoint can stream [event data](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams-data-app.html) about user activity, custom events, and message deliveries for the app.

## Furthermore

- [DealwithData (yt) - End to End Simple Data Analytics Solution using AWS Services](https://www.youtube.com/watch?v=v1qdXQXMp2A)
- [AWS Amplify API / AnalyticsClass](https://aws-amplify.github.io/amplify-js/api/classes/analyticsclass.html)
- [Leveraging Amazon Pinpoint Analytics to Improve Application Performance and User Experience | AWS](https://www.youtube.com/watch?v=fSDQx5ardmI)
- [Data Analytics for Beginners from AWS Experts](https://www.youtube.com/watch?v=IofpKxNRnAE)
- [Web Dev Journey (yt)- Amplify - Analytics](https://www.youtube.com/watch?v=61vlNE4JeaM)
- [Daijiro Wachi (medium) - Improve UX by observability in front-end with Amplify and QuickSight](https://watilde.medium.com/improve-ux-by-observability-in-front-end-with-amplify-and-quicksight-e7083ec1913b)
- [docs.amplify.aws/lib/analytics](https://docs.amplify.aws/lib/analytics/getting-started/q/platform/js/)
- [docs.amplify.aws/start/getting-started/auth](https://docs.amplify.aws/start/getting-started/auth/q/integration/angular/)
