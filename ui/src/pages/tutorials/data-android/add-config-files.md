---
title: "Add Config Files"
description: "In this section, you'll learn how to save and get data on Android using the WeDeploy API Client."
buttonTitle: "I added the config files"
tutorialTitle: "Getting started with WeDeploy Data on Android"
parentId: "data-android"
layout: "tutorial"
time: 60
weight: 4
---

#### Add Config Files

###### container.json

Every service folder must have a `container.json` file that configures the service. Let's add one to our Data Service in the repo we just cloned. 

1. Open the `tutorial-data-android` folder in a code editor.
2. Create a new file inside of the `data` folder and name it `container.json`.
3. Inside of that file, paste this code.

```application/json
{
	"id": "data",
	"type": "wedeploy/data:latest"
}
```

###### api.json

Along with the container.json, each Data service must have an `api.json` file to configure your database (eg. set path, allow certain methods, and require authentication).

1. Go back to `tutorial-data-android` in your code editor.
2. Create another file inside of the `data` folder and name it `api.json`.
3. Inside of that file, paste this code.

```application/json
[
	{
		"path": "/tasks/*",
		"data": true
	}
]
```

<aside>

###### <span class="icon-16-star"></span> Pro Tip

Another thing you can do with your `api.json` file is add other parameters for the collections in your database. One example is to set certain REST methods for each category like this:

```application/json
[
	{
		"path": "/movies/*",
		"data": true,
		"method": ["GET", "PATCH", "PUT", "DELETE"]
	},
	{
		"path": "/shows/*",
		"data": true,
		"method": "POST"
	}
]
```

See the full list of possible <a href="http://wedeploy.com/docs/data/configuring-data.html" target="_blank">data configurations</a>.

</aside>
