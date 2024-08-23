
* Udemy Coupon Grabber & Course Enroller: Grab FREE Coupons!
<br/>

Do you want to LEARN NEW STUFF for FREE? Don't worry, with the power of
web-scraping and automation, this script will find the necessary Udemy Coupons
&amp; enroll you to PAID UDEMY COURSES, ABSOLUTELY FREE!

**NOTE: THIS PROJECT IS NOT AFFILIATED WITH UDEMY.**

**NOTE: THIS PROJECT WILL NOT WORK WITH NON ENGLISH UDEMY.**

<br/>

The code scrapes course links and coupons from:

 - [tutorialbar.com](https://tutorialbar.com)
 - [discudemy.com](https://discudemy.com)
 - [coursevania.com](https://coursevania.com)
 - [freebiesglobal.com](https://freebiesglobal.com)
 - [idownloadcoupon.com](https://idownloadcoupon.com) -> _New_


In case of any bugs or issues, please open an issue in github. Also, don't forget to **Fork & Star the repository if you like it!**

---

## Disclaimer & WARNINGS:

&emsp; 1. Use this ONLY for **Educational Purposes!** By using this code you agree that 
   **I'm not responsible for any kind of trouble** caused by the code. **THIS PROJECT IS NOT AFFILIATED WITH UDEMY.** 
   <br/>
&emsp; 2. **Make sure web-scraping is legal in your region.**
   <br/>
&emsp; 3. This is **NOT a hacking script**, i.e., it can't enroll you for a specific
   course! Instead it finds courses that provide coupon links to make the
   transaction free and then LEGALLY enroll you to the course!

---

## Requirements:

### How to Install the Requirements?

&emsp; __Required Python version:__ [Python 3.8+](https://www.python.org/downloads/)

&emsp; __(Windows users only) Required Microsoft Visual C++ 14.0+ version:__ [Microsoft Visual C++ 14.0+](https://visualstudio.microsoft.com/visual-cpp-build-tools/)

![alt text](https://docs.microsoft.com/answers/storage/attachments/34873-10262.png)

&emsp; __You must have pip or poetry installed. Please look up how to install them in your OS.__

Download a release of this project or clone the repository then navigate to the
folder where you placed the files on. Type `pip install -r requirements.txt` to
get all the requirements installed in one go. Similar instructions applies for poetry.

---

## Instructions

1 . Install from PyPI `pip install udemy-enroller`

-   Run the script and the cli will guide you through the settings required.
-   If you decide to save the settings they will be stored in your home directory: <br>
    **Windows**:
    C:/Users/CurrentUserName/.udemy_enroller<br>
    **Linux**:
    /home/username/.udemy_enroller 
    **The values in settings.yaml should be in the same language as the site you are browsing on.**

<br/>

2 . The script can be passed arguments:

- `--help`: View full list of arguments available
- `--browser=<BROWSER_NAME>`: Run with a specific browser 
- `--discudemy`: Run the discudemy scraper only
- `--coursevania`: Run the coursevania scraper only
- `--tutorialbar`: Run the tutorialbar scraper only
- `--freebiesglobal`: Run the freebiesglobal scraper only
- `--idownloadcoupon`: Run the idownloadcoupon scraper only
- `--max-pages=<NUMBER>`: Max number of pages to scrape from sites before exiting the script (default is 5)
- `--delete-settings`: Delete existing settings file
- `--delete-cookie`: Delete the cookie file if it exists
- `--debug`: Enable debug logging 

<br/>


3 . Run the script in terminal with your target runner:

- `udemy_enroller`
- `udemy_enroller --browser=chrome`
- `udemy_enroller --browser=chromium` 

<br/>

4 . The bot starts scraping the course links from the first **All Courses** page
on [Tutorial Bar](https://www.tutorialbar.com/all-courses/page/1), [DiscUdemy](https://www.discudemy.com/all), [Coursevania](https://coursevania.com) and [FreebiesGlobal](https://freebiesglobal.com) and starts
enrolling you to Udemy courses. After it has enrolled you to courses from the
first page, it then moves to the next site page and the cycle continues.

-   Stop the script by pressing `ctrl+c` in terminal to stop the enrollment process. 

<br/>

5 . *[New]* At the end of process a detailed result is shown:

```
================== Run Statistics ==================

Enrolled:                   56
Unwanted Category:          0
Unwanted Language:          1
Already Claimed:            93
Expired:                    7
Total Enrolments:           1705
Savings:                    €2674.44
================== Run Statistics ==================
```

### Docker

Alternatively you can run the script in docker.

To build the image run:

```
docker build -t udemy_enroller .
```

After the build is finished you can run your container with one of the commands below (you can pass arguments as you would in the cli):

```
docker run -it udemy_enroller 
```

After you entered your login credentials and settings detach from the interactive mode by pressing the `Ctrl-P` followed by `Ctrl-Q`.

You can also create a `settings.yaml` file from the `sample_settings.yaml` and mount to the container with the command:

```
docker run -v $(pwd)/settings.yaml:/home/enroller/.udemy_enroller/settings.yaml udemy_enroller 
```



---
__1. How does the bot work?__

&emsp; The bot retrieves coupon links from [Tutorial Bar](https://www.tutorialbar.com/all-courses/page/1), [DiscUdemy](https://www.discudemy.com/all) and [Coursevania](https://coursevania.com)'s lists to cut the prices and
then uses REST requests to authenticate and enroll to the
courses. Think of it this way: Epic Games & other clients like Steam provide you
a handful of games each week, for free; Only in this case, we need a coupon code
to make those courses free. <br/><br/>
---