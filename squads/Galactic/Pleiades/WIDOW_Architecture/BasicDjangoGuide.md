# Basic Django App and Endpoint Creation Guide

# Purpose

This page contains steps I took to create a new endpoint on the Django backend, specifically the Announcement endpoint needed to show new alerts to the user. This should provide a very basic walkthrough on how to make a very basic app and endpoint. The General model is a very barebones app, so if you want to see a more detailed app I’d reference the Asset app. I’ve also linked the Django documentation at the end of the page and that should help tremendously when making an app and endpoint as well.

## Steps:

- Type Django-admin startapp \*insert app name here\* to create a new react app if needed
  - Make sure the folder structure of the new app is similar to this:
    - <img>
- After you create the new app, go to the base.pyfile in the widow folder and add the app's name to the INSTALLED_APPS array.
  - <img>
- You also want to make sure that the app is listed in the main Dockerfile and the Dockerfile located in the docker_local folder as well.
  - <img>
  - <img>
- After the app is created and the file structure looks similar the above screenshot, create the model you will be using (again, if needed) in models.py. The model should contain the information you want your endpoint to grab.
  - <img>
- After the model is created, add a config class in the app’s apps.pyfile:
  - <img>
- Create your serializer for the model inside of serializers.py. Inside of here is going to be a Meta class that will contain the model used and its fields.
  - <img>
- Next up is creating views. The views.pyfile should contain Python function that will take a web request and return a response. The functions you write in here will be used in your endpoint. Here's an example of what function was used for the announcement endpoint:
  - <img>
- Now you want to take the function you want and import it into urls.py. Here you will choose the name of the endpoint and the function you want to be called when trying to access it.
  - <img>
- After this, go to urls.py in the widow folder, import the url.py from the new app, and add the url.py into the v2_urls_patterns array. The screenshot below shows how this was done with the general app:
  - <img>
- After adding all of these things the endpoint should be working. The last thing you have to do is create tests. The tests you need to write really depend on the app so they’ll differ from app to app. Here’s an example of the test file I wrote to test the serializer:
  - <img>

## Resources:

[Django Documentation](https://docs.djangoproject.com/en/dev/)
