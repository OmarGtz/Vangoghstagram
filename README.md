# Vangoghstagram Android/iOS challenge

**Please build this like you would an actual project you're working on. It should be production-ready code that you're proud of.**

We're looking for awesome engineers to join our team at Instacart.

Your goal today is to build a simple Android app with the following functionality:

* An animated welcome screen that transitions into a view that allows the user to sign into Instacart.
* An authentication screen that captures a user's email and password.
* Validate the user's credentials by making an API call.
* If either field is missing or signin fails, return a relevant error message.
* On a successful signin, store the authentication token returned from the API.

## Guidelines

* Spend a fixed amount of time building the app – less than 3 hours.
* Support for Android phones 4+
* Support for tablet screensizes is a plus
* Test account: staging141508@example.com / test123

## Authentication API

    POST https://staging.instacart.com/oauth/token

### Parameters

client_id
: _Required_ **string** - Your client ID - Use **"nick"**

client_secret
: _Required_  **string** - Your client Secret - Use **"thuglife"**

grant_type
: _Required_  **string** - 'password'

scope
: _Required_  **string** - ''

username
: _Required_  **string** - The email address of the authenticating user

password
: _Required_  **string** - The password of the authenticating user

### Example
    
	curl -X POST -H "Content-Type: application/json" -d '{"username":"staging141508@example.com","password":"test123","client_id":"nick","client_secret":"thuglife","grant_type":"password","scope":""}' https://staging.instacart.com/oauth/token

### Response

	{
    	"access_token"	: "1234",
    	"token_type"	: "bearer",
    	"expires_in"	: null,
    	"refresh_token"	: null,
    	"scope"			: ""
	}


- - -
## Design

### Welcome Screen

You can download the assets for the welcome splash screen [here][]. An example of the welcome screen animation can be found in the Instacart iOS app (kill the app from the background to see the animation).

[here]: https://www.dropbox.com/s/qa676ca3t0rxt29/InstacartAndroidAssets.zip

![Welcome](http://cl.ly/image/0C3z3Y1j0Y3d/InstacartIntro@2x.png)

### Signin Screen

![Sign in](http://cl.ly/image/3G2L0K030B2d/InstacartSignin@2x.png)
