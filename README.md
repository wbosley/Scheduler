# Scheduler
To set up the scheduler, first a Google Cloud Platform project must be created with the Google Calendnar API enabled. Then a Google Calendar API CLIENT ID and API KEY must be created.

These can be obtained by completing the prerequsistes steps for Google's JavaScript quickstart tutorial, available at the link below.

https://developers.google.com/calendar/api/quickstart/js

Once these have been obtained, open index.html and replace the values of the CLIENT_ID and API_KEY vars with your own client id and api keys. These variables are be initialised near lines 1865 and 1866 within index.html.

After placing your own Client ID and API key into the file, go to the directory named SourceCode within cmd, and run this command if you have a version of Python 3 installed:

python -m http.server 8000

...or this command if you have a version of Python 2 installed:

python -m SimpleHTTPServer 8000

...however, this project has not been tested using Python 2, so there may be errors if using Python 2. Please try to use the project using a version of Python 3.

Once the python server is running, go to http://localhost:8000/ in your web browser and the scheduler should be available to use.

 

