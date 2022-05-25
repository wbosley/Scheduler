<h1>Will Bosley Third Year Project 2022: Scheduler</h1>
<h2>SETTING UP THE SCHEDULER</h2>
If you do not already have the files, download SourceCode.zip and unzip the folder.

To set up the scheduler, a Google Cloud Platform project must be created with the Google Calendar API enabled. Then a Google Calendar API CLIENT ID and API KEY must be created.
<br>

To obtain an API key and a Client ID, it is only necessary to complete the bullet points under the heading "Prerequisites" within Google's JavaScript Quickstart tutorial, available at the link below. Upon completing these four bullet points, which have been outlined in red, in the image below, you should have access to your CLIENT ID and your API KEY.

https://developers.google.com/calendar/api/quickstart/js



<img src="Images/download.png" width = "700">



Once these have been obtained, open index.html from inside the SourceCode folder and replace the values of the CLIENT_ID and API_KEY variables with your own client id and api key. These variables are initialized on lines 1865 and 1866 within index.html. Change the values of these variables from "XXXX" to (Your API Key/ Client ID). An image of the variables within index.html that need editing is below.

<img src="Images/apikey.png" width = "550">

After placing your own Client ID and API key into the file, go to the directory named SourceCode within cmd, and run this command if you have a version of Python 3 installed:

python -m http.server 8000

...or this command if you have a version of Python 2 installed:

python -m SimpleHTTPServer 8000

...however, this project has not been tested using Python 2, so there may be errors if using Python 2. Please try to use the project using a version of Python 3.

These lines of code start a very basic Python web server that will be hosting index.html. Once the Python server is running, go to http://localhost:8000/ in your web browser and the scheduler should be available to use.


<h2>USING THE SCHEDULER</h2>

<h4>Scheduling tasks.</h4>

First, log in using a Google account by pressing the "authorize" button in the upper left corner. The position of the authorize button on the page has been outlined in red in the image below.
<img src="Images/login.png" width = "700">

Once you have logged in, you can start scheduling tasks. To add a task, fill in its details in the "form for adding tasks" on the left hand side of the page. When you have specified the task you want scheduled, press the "create task" button at the bottom of the form. If you want to input another task, change the details in the form to the details of your next task and press "create task". An image of this form can be seen below:
<img src="Images/addTasks.png" width = "300">

NOTE: the boxes outlined in red in the image are used for testing, and have no function here, so please do not attempt to fill them in.

Once you've submitted all the tasks you want scheduling, press "schedule tasks" to schedule these to your Google Calendar.

<h4>Setting work hours.</h4>

The default work hours within which tasks will be scheduled for this project is 9am to 5pm. If you want to set custom work hours, fill in the central form with the hours that suit you best. After typing in your work hours and pressing "set work hours", these work hours should be applied next time you generate a schedule by pressing "Schedule tasks" this session. An image of the form for setting your work hours can be seen below.

<img src="Images/workhours.png" width = "300">

<h4>Setting breaks.</h4>

The form on the right labelled "Form for adding breaks" can be used to add breaks into your next schedule. To add a break, fill in the form with the details of your desired break and press "create break". To add multiple breaks, change the details that you previously entered into the break form and press "create break" again. These breaks will be applied to your generated schedule when you press "schedule tasks". The break form can be seen below.

NOTE: PLEASE DO NOT PRESS THE "Schedule break(s)" BUTTON. This is a button for testing, and will refresh your page and reset anything you have inputted into the website. The breaks you have submitted by pressing "create break" will be scheduled in automatically upon pressing "schedule tasks".

<img src="Images/breaks.png" width = "300">

Many apologies for the rough UI. Less focus was put on developing the visuals of the scheduler during development because we were determined to make this application as feature rich as possible within the time available.

<h4>Rescheduling tasks.</h4>

The scheduler has the ability to react appropriately if your plans change, and you need to regenerate your schedule. An example of a scenario like this would be if a user had previously generated a work schedule, and then found out later that they had a hospital appointment stopping them from completing a day’s work tasks. The program can regenerate the user’s schedule to fit in work events around their new calendar. It will reschedule all uncompleted work events in the gaps in the user’s updated Google calendar.

The steps to reschedule any previously scheduled, in progress tasks is as follows. Tick the "reschedule old tasks" button <b>prior</b> to pressing "schedule tasks". If you want to adjust the work hours, add any extra breaks, or upload any new tasks to go along with this reschedule, fill in the appropriate forms before pressing "schedule tasks". 

Please note that scheduling tasks may take a little time, as the Google Calendar API does not allow more than 10 requests per second for developers with free accounts. Please wait for your Google Calendar to update with your schedule before closing or refreshing the webpage. If your Google Calendar is not updating, please try refreshing the Google Calendar web page. (If you want to see the progress of event generation, scroll down to see messages appearing at the bottom of the screen one by one as your events are genarated. If you want to see the progress of event deletion, messages will appear one by one showing the responses to the shceduler's delete requests in your web browsers console. The web broswers console is commonly accessed by pressing F12.)

<h4>Bugs</h4>
Note: There are two bugs which are in the process of being fixed.

There is a bug which can appear when rescheduling tasks. If the current time when the reschedule takes place is within the user’s specified work hours, some events which are scheduled onto that date on the calendar may be erroneously  scheduled in the past. For example, if it's lunchtime, events could be rescheduled in the morning. These erroneously scheduled events may overlap with other calendar events which are positioned earlier in the day. Additionally, they obviously cannot be accomplished if they are in the past. Events which are being rescheduled on the present day should of course only appear in the future. This bug will be fixed in the next update to the code on the Github.

As well as this, there were issues with the times of breaks always being interpreted by the scheduler as being in GMT.  This means that if a break is entered with a time of 1pm to 2pm while it is currently British Summer Time, the breaks will appear between 2pm and 3pm on the user’s calendar. A fix for this is in development.


