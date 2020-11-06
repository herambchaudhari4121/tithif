<img src="./logo/tithif.png" alt="logo" width="233"/>

# tithif

Automate the Facebook website with selenium in python.

Full explained Videos on that project are coming soon. Stay tune with our youtube channel [Noobie Techs](https://www.youtube.com/c/NoobieTechsTithi_mukherjee/)

Table of contents
  * [Contribution and creativity points](#contribution)
  * [Automation ideas](#automation-ideas)
  * [Installation](#installation)
  
## Contribution and creativity points
Selenium automation creativity points 
1. **Debugging** [Example](https://github.com/Tithibots/tithiwa/issues/50#issuecomment-710778130)<br> We can create breakpoints to pause execution at any time then we can try to run some python code in the console to find a way to do something. That helps to develop efficiently.  
2. **CTRL + Left mouse click** [Example](https://github.com/Tithibots/tithiwa/issues/50#issuecomment-710779007)<br> We can see the definitions or references or usages of any function or variable in our IDE like PyCharm. That helps to understand the existing code base efficiently.
3. **Inspect elements and console** [Example](https://github.com/Tithibots/tithiwa/issues/50#issuecomment-710781167)<br> In chrome, we can inspect HTML elements and run javascript code inside console. That helps up to find better selectors and automations steps efficiently.

NOTE: By pressing UP key we can see the history about what codes we had run during Python debugging and inside Chrome's console.<br> 
NOTE: If you are running javascript code inside selenium chromedriver's console then it will **NOT** keep history.<br>
Good luck :)
  
## Automation ideas

* `generate_session(sessionfilename)`: To generate session files with extension `.fb` 
* `open_session(sessionfilename)`: To open session files with extension `.fb`
* `open_chat_to(nameorusername)`: To open chatroom to someone
* `open_chat_to_profile_url(url)`: To open chat to someone from profile url
* `send_message_to_currently_opened_chat(message)`: To Send message to currently opened chatroom
* `send_message_to(nameorusername, message)`: To send message to someone
* `scrape_likes_from_first_n_posts(url)`: To scrape likes of posts of someone  
* `track_online_status(url)`: To track online status for someone and save the data in a file 
* `create_3_days_online_status_wallpaper_from_url(url)`: to show an image visually showing online status for 3-days
* `create_3_days_online_status_wallpaper_from_file(url)`: to show an image visually showing online status for 3-days
* ``

## Facebook Login using Python 

Python scripting is one of the most intriguing and fascinating things to do meanwhile learning Python. Automation and controlling the browser is one of them.

In this particular article, we will see how to log in to the Facebook account using Python and the power of selenium.

Selenium automates and controls browsers and it’s activity. We can code in our way to control browser tasks with the help of selenium. Primarily, it is for automating web applications for testing purposes, but is certainly not limited to just that. Boring web-based administration tasks can be automated as well. As you learn more it’s so much fun to see things happening automatically and saving time in doing useless tasks again and again.

We use selenium here to open the site of our requirement (in this case Facebook) and there we inspect elements across email box, password box, and login button to find the id of them.

Using find_element_by_id() function provided by selenium module, we can find the required element (username box, password box, login button)
Using send_keys() function, provided by selenium module, we will send the data into the box.
Installing third party modules required
Selenium 
getpass
Additional Requirement : geckodriver for firefox and 
                         chromedriver for chrome
## Importing necessary modules
Selenium : to automate browser
Time : to pause running of script for some seconds as browsers try to detect automation stuff if we input too fast
Taking username and password as input from user
Using input() function and passing prompt message as argument.
Opening browser and required website
webdriver.Chrome() will open new window of chrome. We will save it’s object in variable named driver.
Now using get function we will open up the Facebook website.
Finding element for sending data and Sending input
Use inspect element tool on the element of browser of which you want to find id. In this case we will inspect username box, password box, login button to find their id. And then use this id combining with selenium function find_element_by_id() to find it across web page and save it in variables for later use. Then by using send_keys() we will send data across the elements found previously.
Closing the browser
After all of the above steps we have to quit the session and will be achieved by using driver.quit().
Note: Here driver is the name of variable you chose for webdriver.Chrome().
Complete Code:



filter_none
brightness_4
from selenium import webdriver 
from time import sleep 
from webdriver_manager.chrome import ChromeDriverManager 
from selenium.webdriver.chrome.options import Options  
  
usr=input('Enter Email Id:')  
pwd=input('Enter Password:')  
  
driver = webdriver.Chrome(ChromeDriverManager().install()) 
driver.get('https://www.facebook.com/') 
print ("Opened facebook") 
sleep(1) 
  
username_box = driver.find_element_by_id('email') 
username_box.send_keys(usr) 
print ("Email Id entered") 
sleep(1) 
  
password_box = driver.find_element_by_id('pass') 
password_box.send_keys(pwd) 
print ("Password entered") 
  
login_box = driver.find_element_by_id('loginbutton') 
login_box.click() 
  
print ("Done") 
input('Press anything to quit') 
driver.quit() 
print("Finished") 
See how such a concise piece of code can automate things for you.

## Bonus:
We can also enter the password without displaying it on screen, for security purpose. For that we have to include one more module called getpass. Now with just one change in input statement of the password we can input password without displaying it on screen.

filter_none
brightness_4
from getpass import getpass 
pwd = getpass('Enter Password:')  
Getpass prompts the user for a password without echoing. Basically it lets you enter the password without showing it on the screen.

Similarly you can also automate many other things like twitter login, tweeting, Facebook logout, and much more.

In case of any queries, post them below in the comments section. If you liked this article and want to see any more of the similar stuff, let me know in the comments section below.

This article is contributed by Umang Ahuja. If you like GeeksforGeeks and would like to contribute, you can also write an article using contribute.geeksforgeeks.org or mail your article to contribute@geeksforgeeks.org. See your article appearing on the GeeksforGeeks main page and help other Geeks.

Please write comments if you find anything incorrect, or you want to share more information about the topic discussed above.

Attention geek! Strengthen your foundations with the Python Programming Foundation Course and learn the basics.

To begin with, your interview preparations Enhance your Data Structures concepts with the Python DS Course.




## Recommended Posts:
How to access popup login window in selenium using Python
Create MySQL Database Login Page in Python using Tkinter
Gmail Login using Python Selenium
Login Application and Validating info using Kivy GUI and Pandas in Python
Login Twitter using Python Selenium
Login and Registration Project Using Flask and MySQL
Django Sign Up and login with confirmation Email | Python
Python Easy-Login Module
Securing Django Admin login with OTP (2 Factor Authentication)
Python | Automating Happy Birthday post on Facebook using Selenium
Facebook Sentiment Analysis using python
Time Series Analysis using Facebook Prophet
Share Price Forecasting Using Facebook Prophet
Facebook API | Set-2
Facebook API | Set-3
Object Detection with Detection Transformer (DERT) by Facebook
Python | Create video using multiple images using OpenCV
Python | Create a stopwatch using clock object in kivy using .kv file
Image resizing using Seam carving using OpenCV in Python
Python | Visualizing O(n) using Python
