# gp3s-trackuploadAPI

Application developers can use the track upload API to upload track files directly from a device of application to the GPS websites. We use Oauth authentication.


## Information provided to get startted ##

- Authorize Url - This is the endpoint to initiate an authorization for the  Upload API: https://gpsspeedsurfingb2c.b2clogin.com/gpsspeedsurfingb2c.onmicrosoft.com/oauth2/v2.0/authorize?p=B2C_1_signin
- Token Url - This is the endpoint for requesting a token from for the Upload API: https://gpsspeedsurfingb2c.b2clogin.com/gpsspeedsurfingb2c.onmicrosoft.com/B2C_1_signin/oauth2/v2.0/token 


## Information needed ##

- Redirect Url / Callback Url - The redirect Uri for your application.


## You will get back ##

- ClientId: The Client Id of your Client application registered in Gp3s App Registrations. This is typically a GUID value.
- Scope: The scope configured by us for your Client application. 


## Testing and validation ##

Follow this article to retrieve an access token and Refresh Token to validate if the provided information is correct. After validation you can use Oauth 2.0 specifications to implement it in your own application. Make sure you utelize the refresh token.  https://vmsdurano.com/requesting-access-token-from-azure-b2c-with-pkce-using-postman/

If you do not have your application up and running you can use https://sageneric01.z6.web.core.windows.net as the redirect test app. 






