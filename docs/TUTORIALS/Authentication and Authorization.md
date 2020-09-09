
The REST API identifies the user using OAuth 2.0. Use the OAuth endpoints to retrieve the access token required to use the main REST APIs. The OAuth scope will always be all.

The REST API requires that request bodies and responses be in JSON format.<br>

###### Authentication and Authorization

Authentication to the REST APIs is done using OAuth 2.0. CloudLink Center supports the following grant types: implicit and client credentials.<br>

###### Implicit Grant:
The implicit grant type is used by the CloudLink Center UI and can be used by any application that can support redirecting the user to the CloudLink Center login page. This grant type is typically used for a web based interactive session.<br>

###### Client Credentials:
The client credentials grant type can be used by a non-interactive application. A specific set of client credentials is generated within CloudLink Center and embedded within the application. These client credentials are associated with an account but not a specific user. This account has no password associated with it and cannot be logged in interactively. To acquire an access token make a POST request to the token endpoint.<br>

    POST https://%clc_address%/cloudlink/oauth/token?grant_type=client_credentials&client_id=CLIENT_ID&client_secret=CLIENT_SECRET&scope=all


The access token is found in the response body which has the following JSON format:

    {
    "access_token":"eb9d9cf7-bddd-45e7-8e31-ceecb98418e9",
    "token_type":"bearer",
    "expires_in":7199,
    "scope":"all"
    }
<br>
Making Authenticated Requests
Once you have an access token, you can make requests to the API. Add the Authorization header to each request.

Authorization: Bearer eb9d9cf7-bddd-45e7-8e31-ceecb98418e9
<br>

##### Creating a Client User: 
<br>
If using the client credentials grant type, a client user must be created in CloudLink Center. Login to CloudLink Center with a user with the Add User permission and navigate to Configuration, Users. Click Add and specify the Client for the User Type. The User Name is the client_id URL parameter the Password is the client_secret URL parameter in the POST request. A Client user can only login using client credentials grant type, interactive login is prevented.
