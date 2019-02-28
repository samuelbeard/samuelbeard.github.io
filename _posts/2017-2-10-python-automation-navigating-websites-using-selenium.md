---
title: "Python Automation | Navigating Websites Using Selenium"
published: false
---

<!--
Structure

Recording
Exporting
Extracting correct parts.


download firefox addon
record navigation to imdb top movies page.
export the python code
create a new python script and move the code parts into it
loop through the top movies
in the loop get more movie information for each movie of their own page.

Go to Github samuelbeard>blog-series-python-automation>navigating-websites-using-selenium to get the code.

-->

Selenium is a great tool for navigation the web. It can simulate a user clicking on links and typing usernames and passwords and so forth. Though useful, it can be quite slow depending on what computer you are running the script on. It can also take a while to put a script together as it can get quite complicated. In this post, we will put together a script that navigates to a website and gathers some information.

Let's write a script that gets the latest dvd and blu-ray movie releases from the Internet Movie Database and displays them, along with information about them, in the terminal. In another post, we can autonomously tweet these dvd releases.

## Record the Process
Using the Firefox browser and the Selenium add-on, we can record the actions that we want the script to perform then convert them to python automatically. Though we will still have to modify the code it produces, this saves a massive amount of time.

In Firefox, download the (Selenium IDE add-on)[https://addons.mozilla.org/en-GB/firefox/addon/selenium-ide/]

!(selenium ide button)[/images/python-automation-part-1/selenium-ide-button.png]
!(selenium ide button)[/images/python-automation-part-1/selenium-ide-blank.png]

The IDE will open in a new window and will usually begin recording you actions straight away.

While the IDE is recording, navigate to imdb.com, hover over the "Movies, TV and Showtimes" menu item and click on "DVD & Blu-Ray".

*This task might be a bad example of what you can record with the Selenium IDE. It is extremely useful when you want to record a complex task that will be repeated over and over. At least I showed you it exists ay?!*

> #### Selenium IDE Quirks - Two Quick Tips
>> 1. When playing back the task in Selenium, you might notice that it fails to perform the task directly after a navigation to a new page. This is because it starts looking for the next element before the page has loaded. To fix this, add a waitForElementPresent command after the navigation and set the target as something on the new page. Selenium will then wait for that element to be loaded before carrying on.<br>
When we write the python code however, we won't use the code that Selenium exports.
>> 2. When telling Selenium to click on an element, make sure you are using target types what will always exist on the page. You can see how Selenium is finding each element in the "Target" field. Depending on what it is using, this could change and stop your script from working. If possible, use the dropdown menu in the "Target" field to make the script find the element by it's id. This is more likely to be unique and not change.

Once the actions have been recorded, stop the recording by clicking the red button. Then go to `File` > `Export Test Case As...` and select `Python 2 / unittest / WebDriver`. This will export the recording we just did into python code so that we can extract the bits we want easily.

## Export as Python Code

##
