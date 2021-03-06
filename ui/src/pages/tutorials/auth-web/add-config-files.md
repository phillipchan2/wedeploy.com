---
title: "Add Config Files"
description: "In this section, you'll learn how to authenticate users on the web using the WeDeploy API Client."
buttonTitle: "I added the config files"
tutorialTitle: "Getting started with WeDeploy Auth on the web"
parentId: "auth-web"
layout: "tutorial"
time: 60
weight: 4
---

#### Add Config Files

Every service folder must have a `container.json` file that configures the service. Let's add one to our Auth and Hosting Services in the repo we just cloned. 

##### Auth 

1. Open the `tutorial-email-web` folder in a code editor.
2. Create a new file named `container.json` inside the `auth` folder.
3. In that file, paste this code:

```application/json
{
	"id": "auth",
	"type": "wedeploy/auth",
	"env": {
		"WEDEPLOY_AUTH_SECURE_FIELDS": "password",
		"WEDEPLOY_AUTH_PASSWORD": "true"
	}
}
```

##### Hosting 

1. Change to the `hosting` folder and create another `container.json` file
3. In that file, paste this code:

```application/json
{
	"id": "hosting",
	"type": "wedeploy/hosting"
}
```

<aside>

###### <span class="icon-16-star"></span> Pro Tip

One of the awesome things you can do in your `container.json` file is add environment variables. There are many ways to use these; one example is to provide Google sign-in for your users.

```application/json
{
	"id": "auth",
	"type": "wedeploy/auth",
	"env": {
		"WEDEPLOY_AUTH_SECURE_FIELDS": "password",
		"WEDEPLOY_AUTH_PASSWORD": "true",
		"WEDEPLOY_AUTH_GOOGLE": "true",
		"WEDEPLOY_AUTH_GOOGLE_CLIENT_ID": "<your-google-app-id>",
		"WEDEPLOY_AUTH_GOOGLE_CLIENT_SECRET": "<your-google-app-secret>"
	}
}
```

See the full list of <a href="http://wedeploy.com/docs/auth/environment-variables.html" target="_blank">Environment Variables for Auth</a>.


</aside>
