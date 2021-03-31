## Milestone 4 – Keep Rolling Website

I am creating a website for Brazilian Jiu Jitsu enthusiasts to purchase instructionals/courses and clothing/merchandise.

## UX

_Overview_

The aim of the project is to create an ecommerce website where users can purchase items of their choice. 
The website is created for those who train Brazilian Jiu Jitsu, who are often looking for courses/instructional material they can use to improve their game, especially in recent times where many are in lockdown, and unable to train Jiu Jitsu.
The website will also sell Jiu Jitsu merchandise, such as clothing they can use whilst training.
Users will want to easily be able to browse and purchase items, and the website owner will want to showcase their products postiviely to drive sales. 
The website is designed to be suitable for use on all devices, from desktop to mobile. 
Due to timing constraints, I will be taking the approach of producing a minimum viable product for this project submission, with the aim of improving/further developing the site in the future.

_User Stories_

As a user of the site:

	*	I want to understand the website's purpose
	*	I want to be easily able to view a list of all products by category
	* 	I want to be able to view specific product details
	*	I want to be easily able to purchase products

As the site owner:

	* 	I want the website to provide a platform for users to purchase items
	*	I want to be able to add/edit/delete products

_5 S's_

**Strategy** 

The primary goal is to create a ecommerce website for Brazilian Jiu Jitsu enthusiasts to purchase instructionals/courses and clothing/merchandise.

**Scope** 

The overall look and feel of the website was influenced by researching similar websites (credits at end):
    -   These are simple/clean in design
    -   There is a hero image explaining the site's purpose, along wih some introductory text
    -   There is a menu where you can display product listings by category (usually on the navbar)
    -   There is an icon to login and/or display your shopping bag on the navbar
    -   Products are listed in a "grid" style with each product having it's own image and high-level description
    -   Clicking on the product image takes you to the product page with it's detailed description
    -   There is a search box to search for products (usually on the navbar)
    -   Selected items are placed in a "shopping bag" page where users can see items selected for purchase before confirming their buy

**Structure** 

**Skeleton** 

**Surface** 


## Deployment

The source code for this site is in GitHub. Heroku was used to deploy the site. AWS is used to store files.

_Github_

The source code for this site is in GitHub.

To clone the code from GitHub:

1.	On GitHub, navigate to the main page of the repository.
2.	Above the list of files, click Code.
3.	To clone the repository using HTTPS, click HTTPS under "Clone".
4.	Open Git Bash.
5.	Change the current working directory to the location where you want the cloned directory.
6.	Type git clone, and then paste the URL you copied earlier:
    ```$ git clone https://github.com/YOUR-USERNAME/MS4_KeepRolling.git```
7.	Press Enter to create your local clone.
8.  Create your own env.py file to store variables, and ensure this is listed in your .gitignore file to keep these from being displayed publicly.

_Deployment to Heroku_

Heroku is used to deploy the app:

1.	When logged into your account, create new app:
    ![Picture1](static/readme-image/Picture1.png)

2.	Choose app name and your closest region
	![Picture2](static/readme-image/Picture2.png) 

3.	On Resources tab, provision Heroku Postgres (use the free plan)
    ![Picture3](static/readme-image/Picture3.png) 
	 
4.	Back in gitpod, install the following via these commands:
	 - ```pip3 install dj database url```
	 - ```pip3 install psycopg2 binary```

5.	Freeze the requirements so this is updated in the requirements.txt file to make sure Heroku installs all apps when deployed:
	- ```pip3 freeze > requirements.txt```

6.	To get stores database setup, go to settings.py an import dj_database_url:
    ![Picture6](static/readme-image/Picture6.png) 

7.	Down in the databases setting, comment out default configuration and replace the default database with a call to dj_database_url.parse, and give it the database URL from Heroku in the brackets (from your config variables in your app settings tab): 
    ![Picture7](static/readme-image/Picture7.png) 

8.	Now run all migrations again, by running:
	- ```python 3 manage.py migrate```

9.	Then create a superuser to log in with:
	- ```python3 manage.py create superuser```

10.	Back in settings.py remove the Heroku database config, and uncomment the original so our database URL doesn't end up in version control:
    ![Picture10](static/readme-image/Picture10.png) 

11.	Then commit to github.

12.	Use an if statement in settings.py, so when app is running on Heroku, where database URL environment variable is defined, we connect to Postgres, otherwise we connect to sqlite:
    ![Picture12](static/readme-image/Picture12.png) 

13. Install unicorn, which will act as our webserver, then freeze that into requirements.txt:
	- ```pip3 install gunicorn```
	- ```pip3 freeze > requirements.txt```

14.	Now create Procfile, and enter the following to tell Heroku to create a web dyno, which will run unicorn and serve our django app:
	```web: gunicorn APP_NAME.wsgi:application```

15.	Temporarily disable collectstatic:
    ![Picture15](static/readme-image/Picture15.png) 

16.	Add the hostname of our Heroku app to allowed hosts in settings.py, add localhost aswell:
	ALLOWED_HOSTS = ['YOUR-APP-NAME.herokuapp.com', 'localhost']

17.	Then add/commit changes to github.

18.	To deploy to Heroku, enter (you may need to initialize your Heroku git remote if you created your app on the website rather than the CLI):
    ![Picture18](static/readme-image/Picture18.png) 

19.	To automatically deploy on Heroku when we commit to github, on your Heroku dashboard go to Deploy > select Github, and search for your repository, then click Connect:
    ![Picture19](static/readme-image/Picture19.png) 

20.	Click to enable automatic deploys:
    ![Picture20](static/readme-image/Picture20.png) 

21.	You need a new secret key to enter in you Heroku Config Vars (you can use an online Django secret key generator to do this):
    ![Picture21](static/readme-image/Picture21.png) 

22.	Now you can replace the secret key in settings.py with a call to get this from the environment:
    ![Picture22](static/readme-image/Picture22.png) 

23.	Commit/push these changes to github
