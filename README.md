# Gp3s track upload API

Application developers can use the track upload API to upload track files directly from a device of application to the GPS websites. We use Oauth/Oidc authentication on the API. So the service to service communication will use the Gp3s users access token to authenticate on behalve of the GP3S user. 


#Authentication and Authorization process:

Gp3s open platform is based on OAuth 2.0 protocol. The Authorization process consists of 4 parts. 
1. Guide the user to the authorization page to agree to the authorization and obtain the token
2. The accessToken is valid for 1 day by default. If necessary, the developer can refresh the authorized accessToken to avoid expiration.
3. Use accessToken for available API.


## Information provided to get startted with Authentication ##

### Information needed ###

Please sent us a request with detailed info to begin the API request reviewing process.

1. Company Name
2. Company URL
3. Application Name
4. Application Logo (200 px by 200 px)
5. Application Description (Limit 100 characters)
6. Authorized Callback Domain (redirect_uri), provide one or more

### You will get back ###

After reviewing we get back to you with the ClientID and the scope that you should use in your application to call the API. This information will be limitted to the explicith use of the upload api for tracks.

1. ClientId: The Client Id of your Client application registered in Gp3s App Registrations. This is typically a GUID value.
2. Scope: The scope configured by us for your Client application. 


### Building your app ###

Follow this article to retrieve an access token and Refresh Token to validate if the provided information is correct. After validation you can use Oauth 2.0 specifications to implement it in your own application. Make sure you utelize the refresh token. see for more details:  [article](https://vmsdurano.com/requesting-access-token-from-azure-b2c-with-pkce-using-postman/)

Endpoints:
1. Authorize Url - This is the endpoint to initiate an authorization for the  Upload API: https://gpsspeedsurfingb2c.b2clogin.com/gpsspeedsurfingb2c.onmicrosoft.com/oauth2/v2.0/authorize?p=B2C_1_signin
2. Token Url - This is the endpoint for requesting a token from for the Upload API: https://gpsspeedsurfingb2c.b2clogin.com/gpsspeedsurfingb2c.onmicrosoft.com/B2C_1_signin/oauth2/v2.0/token 


If you do not have your application up and running please use the code provided in this repository for building a test app. 



# Calling the Track Upload API #

1. make sure you are registered as developer, go to https://apimgp3s.portal.azure-api.net/ to register with your gps-speedsurfing account
2. register for the GP3S professional products
3. Go to the Track-upload api to explore, you cannot test the api from this portal (file upload is blocked)
4. The API url: [https://apimgp3s.azure-api.net/track-upload/Gp3s_upload_rawtrack](https://apimgp3s.azure-api.net/track-upload/upload_rawtrack)
5. Provide the file in the body as form-data
6. Provide additional headers:
   - Ocp-Apim-Subscription-Key {you can get this from the Api portal when you have signed up for GP3S professional product}
   - Authorization {token}
8. Provide additional information in the body as form-data
   - filename {name of the file uploaded}
   - provider {application name}
   - filetype {fit,gpx,sbn,oao}

## You can test with postman:

Get an access token:
![postman get token](https://gp3scdnstorage.blob.core.windows.net/gp3s/cdn/img/postman-get-accesstoken.png)

Click "Get New Access Token", a browser popup will appear where you have to provide the gp3s user credetials, once completed the access token will return.
You can now use the access token to upload a track.

Call the API with the access token:
![postman get token](https://gp3scdnstorage.blob.core.windows.net/gp3s/cdn/img/postman-call-api.png)



