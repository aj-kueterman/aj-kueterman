Key Files
Here's where most of the logic for auth takes place:

AuthorizationInterceptor	OkHttp Interceptor that adds auth tokens to every request & handles refreshing tokens when needed.
AuthenticationFailedInterceptor	OkHttp Interceptor that checks the response of every call for 401's, and triggers a broadcast to the UserUnAuthorized receiver when there is one.
UserUnAuthorized	The BroadcastReceiver that handles sign-out intents as a result of 401's and signs out a user with the SignOutManager. This class also launches the HomeActivity and indicates a sign-in required.
SignOutManager	Handles sign out in a suspending function. Clears out a bunch of user data and auth state & logs out from MSAL.
MsalRepo / MsalRepoImpl	Interface mostly with the IMultipleAccountPublicClientApplication to initialize the MSAL, sign out, refresh tokens, and check the status of auth.
MsalEntrlyPoint / MsalEntrlyPointImpl	Check isMSALInitialized and launchMSALSignIn. Launching sign in takes an activity, callback, and source of the call. The Impl calls into the MsalRepo to interact with the MSAL app. 
OAuthServiceManager	
Orchestrates the refreshing of tokens for both IDP and B2C auth flows. 



IMultipleAccountPublicClientApplication

This is the MSAL code that defines the API with the MSAL library. Used by the MsalRepoImpl.
KrogerUserManagerComponent

Stores the KrogerUser which manages user credentials.
...


