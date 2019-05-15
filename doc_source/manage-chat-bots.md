# Managing Chat Bots<a name="manage-chat-bots"></a>

If you administer an Amazon Chime Enterprise account, you can create up to 10 chat bots for integration with Amazon Chime\. Chat bots can only be used in chat rooms created by members of your account\. Only chat room administrators can add chat bots to a chat room\. After a chat bot is added to a chat room, members of the chat room can interact with the bot using commands provided by the bot creator\. For more information, see [Using Chat Bots](https://docs.aws.amazon.com/chime/latest/ug/chat-bots.html) in the *Amazon Chime User Guide*\.

## Integrating Chat Bots with Amazon Chime<a name="integrate-bots"></a>

Before you begin, complete the following tasks:
+ Create a chat bot to be integrated with Amazon Chime\.
+ Create the outbound endpoint for Amazon Chime to send events to your bot\. Choose from an AWS Lambda function ARN or an HTTPS endpoint\.

**Important**  
We recommend the following best practices when assigning DNS for your HTTPS endpoint:  
Use a DNS subdomain that is dedicated to the bot endpoint\.
Use only A\-records to point to the bot endpoint\.
Protect your DNS servers and DNS registrar account to prevent domain hijacking\.
Use publicly valid TLS intermediate certificates that are dedicated to the bot endpoint\.
Cryptographically verify the bot message signature prior to acting on a bot message\.

For more information about Lambda, see the *[AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/)*\.

After creating your chat bot, use the Amazon Chime API with the AWS SDK or AWS Command Line Interface \(AWS CLI\) to do the following:
+ Integrate your chat bot with Amazon Chime\.
+ Configure the outbound endpoint for Amazon Chime to send events to your bot\.

You can also use the Amazon Chime API to enable or stop chat bots for your Amazon Chime account\. For more information about using the Amazon Chime API, see the [https://docs.aws.amazon.com/chime/latest/APIReference/Welcome.html](https://docs.aws.amazon.com/chime/latest/APIReference/Welcome.html)\.

Chat bots cannot be deleted\. To stop a chat bot from being used in your account, use the Amazon Chime [UpdateBot](https://docs.aws.amazon.com/chime/latest/APIReference/API_UpdateBot.html) API action in the *Amazon Chime API Reference*\. When you stop a chat bot, chat room administrators can remove it from a chat room, but they cannot add it to a chat room\. Users who @mention a stopped chat bot in a chat room receive an error message\.

**To integrate a chat bot with Amazon Chime**

1. Use the Amazon Chime [CreateBot](https://docs.aws.amazon.com/chime/latest/APIReference/API_CreateBot.html) API action in the *Amazon Chime API Reference* to integrate a chat bot with your Amazon Chime Enterprise account\.

   1. Enter a chat bot display name of up to 55 alphanumeric or special characters \(such as \+, \-, %\)\.

   1. Enter the registered domain name for your Amazon Chime Enterprise account\.

1. Amazon Chime creates a chat bot ID for your account and assigns it an email address that looks like this: `displayName-chimebot@example.com`\. When the chat bot is added to an Amazon Chime chat room, it appears in the roster as `BotDisplayName (Bot)`\. 
**Note**  
Bot names and email addresses cannot be changed\.

1. Use the Amazon Chime [PutEventsConfiguration](https://docs.aws.amazon.com/chime/latest/APIReference/API_PutEventsConfiguration.html) API action in the *Amazon Chime API Reference* to configure the outbound HTTPS endpoint for your chat bot\. Enter one of the following:
   + A Lambda function ARN
   + An HTTPS endpoint

1. One of the following occurs:
   + **For a Lambda function ARN** – Amazon Chime calls Lambda to add permission to allow the Amazon Chime administrator's AWS account to invoke the provided Lambda function ARN\. This is followed by a dry run invocation to verify that Amazon Chime has permission to invoke the function\. If adding permissions fails or if the dry run invocation fails, then the `PutEventsConfiguration` request returns an HTTP 4xx error\. 
   + **For an HTTPS endpoint** – Amazon Chime verifies your endpoint by sending an HTTP Post request with a Challenge JSON payload to the outbound HTTPS endpoint that you provided in the previous step\. Your outbound HTTPS endpoint must respond by echoing back the Challenge parameter in JSON format\. The following examples show the request and a valid response\.  
**Example Request from Amazon Chime to the outbound HTTPS endpoint**  

     ```
                    HTTPS POST 
     
                    JSON Payload:
                    {
                       "Challenge":"00000000000000000000",
                       "EventType" : "HTTPSEndpointVerification"
                    }
     ```  
**Example Valid Response from outbound HTTPS endpoint to Amazon Chime**  

     ```
                    HTTP/1.1 200 OK
                    Content-type: application/json
     
                    {
                        "Challenge":"00000000000000000000"
                    }
     ```

     If the challenge handshake fails, then the `PutEventsConfiguration` request returns an HTTP 4xx error\.

1. Provide the chat bot's email address to your chat room administrators, along with any other instructions necessary to add it to a chat room\.

1. Provide the chat bot commands to your chat room users\. One way to do this is to program your chat bot to send command help to the chat room when it receives the chat room invite\. We also recommend creating a Help command for your chat bot users to use\.

For instructions on how chat room administrators can add a chat bot to a chat room, see [Adding a Chat Bot to a Chat Room](https://docs.aws.amazon.com/chime/latest/ug/chat-bots.html#add-bot-chat) in the *Amazon Chime User Guide*\.

**Note**  
If the outbound HTTPS endpoint for your bot is not configured or is empty, chat room administrators cannot add the bot to a chat room, and chat room users cannot interact with the bot\.

## Authenticating Chat Bot Requests<a name="auth-bots"></a>

You can authenticate requests sent from Amazon Chime to your chat bot by computing a signature based on the request\. Then, validate that the computed signature matches the one on the request header\. Amazon Chime uses the HMAC SHA256 hash to generate the signature\.

If your chat bot is configured for Amazon Chime using an outbound HTTPS endpoint, follow the authentication steps below\.

**To validate a signed request from Amazon Chime for a chat bot with a outbound HTTPS endpoint configured**

1. Get the **Chime\-Signature** header from the HTTP request\.

1. Get the **Chime\-Request\-Timestamp** header and the **body** of the request\. Then, use a vertical bar as the delimiter between the two elements to form a string\.

1. Use the **SecurityToken** from the CreateBot response as the initial key of **HMAC\_SHA\_256**, and hash the string that you created in step 2\.

1. Encode the hashed byte with Base64 encoder to a signature string\.

1. Compare this computed signature to the one in the **Chime\-Signature** header\.

The following code sample demonstrates how to generate a signature using Java\.

```
        private final String DELIMITER = "|";
        private final String HMAC_SHA_256 = "HmacSHA256";
   
        private String generateSignature(String securityToken, String requestTime, String requestBody) 
        {
            try {
                final Mac mac = Mac.getInstance(HMAC_SHA_256);
                SecretKeySpec key = new SecretKeySpec(securityToken.getBytes(UTF_8), HMAC_SHA_256);
                mac.init(key);
                String data = requestTime + DELIMITER + requestBody;
                byte[] rawHmac = mac.doFinal(data.getBytes(UTF_8));

                return Base64.getEncoder().encodeToString(rawHmac);
                } 
            catch (Exception e) {
                throw e;
                }
         }
```

The outbound HTTPS endpoint must respond to the Amazon Chime request with `200 OK` within 2 seconds\. Otherwise, the request fails\. If the outbound HTTPS endpoint is unavailable \(because of a Connection or Read timeout\) after 2 seconds, or if Amazon Chime receives a 5xx response code, Amazon Chime retries the request two times\. The first retry is sent 200 milliseconds after the initial request fails\. The second retry is sent 400 milliseconds after the previous retry fails\. If the outbound HTTPS endpoint is still unavailable after the second retry, the request fails\.

**Note**  
The **Chime\-Request\-Timestamp** changes each time the request is retried\.

If your chat bot is configured for Amazon Chime using a Lambda function ARN, follow the authentication steps below\.

**To validate a signed request from Amazon Chime for a chat bot with a Lambda function ARN configured**

1. Get the **Chime\-Signature** and **Chime\-Request\-Timestamp** from the Lambda request **ClientContext**, in Base64 encoded JSON format\. 

   ```
   {
   "Chime-Signature" : "1234567890",
   "Chime-Request-Timestamp" : "2019-04-04T21:30:43.181Z"
   }
   ```

1. Get the **body** of the request from the request payload\.

1. Use the **SecurityToken** from the `CreateBot` response as the initial key of **HMAC\_SHA\_256**, and hash the string you created\.

1. Encode the hashed byte with Base64 encoder to a signature string\.

1. Compare this computed signature to the one in the **Chime\-Signature** header\. 

If a `com.amazonaws.SdkClientException` occurs during the Lambda invocation, Amazon Chime retries the request two times\.

## Managing Chat Bots<a name="manage-bots"></a>

As the Amazon Chime account administrator, you can use the Amazon Chime API with the AWS SDK or AWS CLI to view your chat bot details and enable or stop your chat bots from being used in your account\. You can also regenerate security tokens for your chat bot\. 

For more information, see the following topics in the *Amazon Chime API Reference*:
+ [GetBot](https://docs.aws.amazon.com/chime/latest/APIReference/API_GetBot.html) – Gets your chat bot details, such as bot email address and bot type\.
+ [UpdateBot](https://docs.aws.amazon.com/chime/latest/APIReference/API_UpdateBot.html) – Enables or stops a chat bot from being used in your account\.
+ [RegenerateSecurityToken](https://docs.aws.amazon.com/chime/latest/APIReference/API_RegenerateSecurityToken.html) – Regenerates the security token for your chat bot\.

You can also choose to change the `PutEventsConfiguration` for your chat bot\. For example, if your chat bot was initially configured to use an outbound HTTPS endpoint, you can delete the previous events configuration and put a new events configuration for a Lambda function ARN\.

For more information, see the following topics in the *Amazon Chime API Reference*:
+ [DeleteEventsConfiguration](https://docs.aws.amazon.com/chime/latest/APIReference/API_DeleteEventsConfiguration.html)
+ [PutEventsConfiguration](https://docs.aws.amazon.com/chime/latest/APIReference/API_PutEventsConfiguration.html)

## Amazon Chime Events Sent to Chat Bots<a name="events-bots"></a>

The following events are sent to your chat bot from Amazon Chime
+ **Invite** – Sent when your chat bot is added to an Amazon Chime chat room
+ **Mention** – Sent when a user in a chat room @mentions your chat bot
+ **Remove** – Sent when your chat bot is removed from an Amazon Chime chat room

The following examples show the JSON payload sent to your chat bot for each of these events\.

**Example Invite Event**  

```
            {
              "Sender": {
                            "SenderId": "user@example.com",
                            "SenderIdType": "EmailId"
                         },
              "Discussion": {
                            "DiscussionId": "abcdef12-g34h-56i7-j8kl-mn9opqr012st",
                            "DiscussionType": "Room"
                            },
              "EventType": "Invite",
              "InboundHttpsEndpoint": {
                                        "EndpointType": "Persistent",
                                        "Url": "https://hooks.a.chime.aws/incomingwebhooks/a1b2c34d-5678-90e1-f23g-h45i67j8901k?token=ABCDefGHiJK1LMnoP2Q3RST4uvwxYZAbC56DeFghIJkLM7N8OP9QRsTuV0WXYZABcdefgHiJ"
                                      },
              "EventTimestamp": "2019-04-04T21:27:52.736Z"
            }
```

**Example Mention Event**  

```
            {
                "Sender": {
                            "SenderId": "user@example.com",
                            "SenderIdType": "EmailId"
                          },
                "Discussion": {
                                "DiscussionId": "abcdef12-g34h-56i7-j8kl-mn9opqr012st",
                                "DiscussionType": "Room"
                              },
                "EventType": "Mention",
                "InboundHttpsEndpoint": {
                                            "EndpointType": "ShortLived",
                                            "Url": "https://hooks.a.chime.aws/incomingwebhooks/a1b2c34d-5678-90e1-f23g-h45i67j8901k?token=ABCDefGHiJK1LMnoP2Q3RST4uvwxYZAbC56DeFghIJkLM7N8OP9QRsTuV0WXYZABcdefgHiJ"
                                        },
                "EventTimestamp": "2019-04-04T21:30:43.181Z",
                "Message": "@botDisplayName@example.com Hello Chatbot"
            }
```

**Note**  
The `InboundHttpsEndpoint` URL for a Mention event expires 2 minutes after it is sent\.

**Example Remove Event**  

```
            {
                "Sender": {
                            "SenderId": "user@example.com",
                            "SenderIdType": "EmailId"
                          },
                "Discussion": {
                                "DiscussionId": "abcdef12-g34h-56i7-j8kl-mn9opqr012st",
                                "DiscussionType": "Room"
                              },
                "EventType": "Remove",
                "EventTimestamp": "2019-04-04T21:27:29.626Z"
            }
```