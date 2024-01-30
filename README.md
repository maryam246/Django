# MVT (Model View Template)
- MVT is software design pattern
- Collection of 3 imp components MVT
- **Model(Database)**: Model is going to act as the interface of your data.(any data to store, work with database handle all the data base)
- **View(functions)**: is the user interface--what you see in your browser you render a website.
   - View is the python function used to handle the web request.
- **Template**: it contain the static content like HTML,CSS and Javascript.

## Setup django
in terminal pass this cammand
- pip install django

after install check in system django is install or not by this command.
- pip freeze
 By this command
 - django-admin
 all command about django is appear.
## How to setup new project
 Then choose the startproject command keyword to start website project like this,
 - django-admin startproject MyWebsite

 here, you can keep any other name instead of MyWebsite which you want.

# ================2nd day================

 ## Starting a Development Server
 By this command
 - python manage.py runserver

 Then copy the url which is generated by the above command and open this url in browser.

 - By press the Cntrl c the server stop
 To change the url code use this command.
 - python manage.py runserver 1234

where, i write 1234 you can chosse your own decided number which you want.
## Python Django Structure
The main concept of this topis is, where we can place our html, css, javasript files and also learn where urls make and keep.

### Folder Structure
In  main folder 'db.sqlite3' file is made when we migrate. sqlite use default database of django.
- make **templates** folder in which we keep all html files.
- make **static folder** in which we keep all static data like CSS , Javascript , IMAGES ,Fonts.
- make **media**  keep all dynamic files, like dynamic images.
## How to  migrate default Migrations?
- Default Migrations:
    - Some tabels schema is by default is created.
    - To open admin panel we make the super user who able to open admin panel. So, to create super user we should first migrate.
    - Thier is 2 commands 1st one is:
    - **python manage.py makemigrations** it used when make new model to convert in migration through makemigration.After that we use this below command for migrations,
    - **python mange.py**
    - we do not need to create migrations beacuse already default migrationis present.
    - Our main logic by migrate to create table.

### Download db
- To see all data in sqlite.

# ================3rd day================
## Create Superuser in Django
By this command
**python manage.py createsuperuser**

after running this above command it take some inputs in terminal. like this
- (Username (leave blank to use 'ammarakhanam'): admin
Email address: testing@gmail.com
Password:
Password (again):
Superuser created successfully.
)
## Urls & Views
Urls(Route) is also called Routes.
like (

    https://www.MyWebsite.com/ ----> Showing starting page

    https://www.MyWebsite.com/blog/ ---->Show list of all posts

    https://www.MyWebsite.com/blog/siglepost ---->Show Specify post
)

- Views:
   -The logic executed for different URLs (https Method)

            - Functions         - Class
views is bassically connect with urls, when user open the urls then url hit the view which associate those urls.
- so, for connecting purpose of urls, and view we make the urls.py in which we define all urls.py file and also make the view.py file in which we create our class and funtion.

## Creating Django URLs & Views
- To show the response of urls on site we use HttpRespons in views.py.
In our main project name same name file exist in my creating website the name is MyWebsite inside this same name file MyWebsite is present in which we create the views.py file. in which you create python functions and classes.
- We will create as many URLs on our website as the number of views we generate
- To display the view on site first we import the views.py in urls.py, then set the function view path in urls.py.

## Create dynamic URLs in Django
Dynamic routes/urls is create in three ways.
- int
- starting
- slug  (slud type data is like this hello-My-Website)

## Render a HTML templates as response
- create html page-->in templates
- connect the html file---> in settings.py
- make function---> in viwes.py 
  -for this purpose import **from django.shortcuts import render**

- all html data is store in templates file which we created in starting.
- To Render a HTML templates as response, For this purpose we import the library.It renderd the html page.
    - **from django.shortcuts import render**
    - render takes two argument 1st paremeter is 
       - request     and 2nd is  - Your page name
- In setting.py folder in this templates directory is set.
- In setting.py folder goes in  Templates varible. in this variable directory is present with this name ** DIRS** 
- in directory keep templates in directory. like this
   - [BASE_DIR,"templates"]

## Difference btw HttpRespons AND Render
-Render is usally used to load the templates or context, on the other hand, HttpRespons is ually for data.
- HttpRespons is not able to call the Html page,
but render is able to call the html page.
- If you want just show the text on website use HttpRespons.
- if you want to call the html page then impoer render module from django.shortcuts. 

# ================4th day================
## Passing data from a Django View to a template
- In viwes file 1 more argument is add wich it dictonary name in **return render**.
- In this all data like title, or main html text is not directely write in html file. Instead write in html we write in **Viwes.py** file in dictonary manner and pass the data **key** in html page in double **curly brackets{{}}**.
## Django Template For Loop
data like list from django is iterate by loop use in html file like this.
- Structure of for loop in template.
    - {% for n in clist%}

               ......

    {% endfor %}
- (
   <body>
    {% for n in clist%}
    <div>{{forloop.counter0}} {{n}}</div>
    {% endfor %}
    </body>
    
    )
- Here, clist (contain list) is the variable which is present in viwes/Django file.
- To fetch dictonary throug loop method is different.
## Django Template Using if..elif..else
- Structure of **if** statement in Django Template is:

    - {% if n > 20 %}

        ......statement

      {% endif %}

- Structure of **if else** statement in Django Template is:
   - {% if numbers | length > 0 %}
     
      ......statement

     {% else %}
         
         ....statement
   
     {% endif%}
- Structure of **if , else ,elif** statement in Django Template is:
   -  {% if numbers | length > 0 %}
     
      ......statement

      {% elif %}
         
         ....statement

      {% elif %}
         
         ....statement

     {% else %}
         
         ....statement
   
     {% endif%}

# ================5th day================

## Managing static files (e.g. images, JavaScript, CSS)STATICFILES_DIRS

- In this all html files we put in templates file, and all other files like(CSS,JS,IMG,FONTS) put in static folder.
- Now, we connect html files in views.py.
- To connect the statics files we set the directory in setting.py.
   - we set the static path in setting.py like this.

      - STATICFILES_DIRS = [

    BASE_DIR , "static",  

    "/var/www/static/",

]

here, static is the folder name in which all files (css,img,fonts) is present.
- To check static file is called in browser by this
    - http://localhost:1234/static/css/index.css

      - here,static is folder and css is static file in which index name css file is present.
- one more method we can use insted of setting path manually like this:
  -<img src="/static/./img/features.png" alt="" />
  
  - we use for each static files data. is this 
     - {% load static %} use at the top of html file
     - use this like this:
        - <img src="{% static './img/features.png' %}" alt="" />

## Header and Footer in djano HTML Template
In website multipages have same header and footer so, insted we coding the same code  for each page, we make seperately html file in which we code for header and footerin seprate files. which we can use in multiple pages of website.

By this keyword **include**.
- {% include "header.html" %}
- {% include "footer.html" %}

# ================6th day================

## extends - Django Template Tags
In this we don't include the header and footer file in each html file, instead this the header and footer are present at the same position but the inner content is changed according to different html file. content.
- For this purpose we made the **base.html** file in template file.
- We include the header and footer in the base file.
- inner side of header and footer we use block code in base file through which we dynamically change the content of different html files.
     - The code is :
           - {% include "header.html" %}

{% block content %}

{% endblock %}

{% include "footer.html" %}

here, content is the name. this name is use where weextend base.html.

- in main.html and other html file extend this base file like this:
   - {% extends "base.html" %}
   - {% block content %}
        - ...content..
   - {% endblock %}

## Django URL Template Tags
We direct use the / before the each part url in header file. but developers use this below urls method. both work same.

- In urls.py file in path set all path like this :
 
   - path('',views.homePage, name='home'),
   - path('features/',views.features, name='features'),

And also make changes in header.html file like this:
   - <li><a href="{% url 'home' %}">Home</a></li>
   - <li><a href="{% url 'features' %}">Features</a></li>

# ================7th day================
## How to Highlight Active Links in Django
In this we heiglight those page link which is currentlly active.
- for this purpose we make the class in css file and this class name is use in our li tag.
   - Class which i made in css file is like this:
       - header .active a{
    
    background-color: red;

}
- We use **{{request.path}}** which give the exactly path of the active open page. after that we apply if else conditon which able to active the current open page.
   - Like this static way:
       - <li class="{% if request.path == '/' %} active {% endif %}"><a href="{% url 'home' %}">Home</a></li>

   - The other way which work same and more efficient and use by programmer is by url:
       - {% url 'contact' as url %}

          <li class="{% if request.path == url %} active {% endif %}"><a href="{{url}}">Contact</a></li>

## HTTP Request methods
### Get Method
- Get method send the user fill data append to the (url) page request.The page and encoded information is seperate by this ? chracter.
- Restricted only upto 1024 chracters is send.
- **Never use Get Method** for password or other sensitive information.
- Cannot be used to send the binary data, like Images, word documents, to the server.

### Post Method
- The **Post method** transfers informations through/via HTTP headers.  
- It is secure method.
- Does not have Restriction.
- Can be used send to send ASCII as well as binary data.
- Post method follow the HTTP protocol.
## Implement Form with Get Method
- In viwes.py code we use this get method in 2 ways 1st one is:
n1= int(request.GET['num1'])

  n2 = int(request.GET['num2'])

- 2nd one is:
n1 = int(request.GET.get('num1'))

n2 = int(request.GET.get('num2'))
## Post Method With CSRF Token
