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
- In this method we also fill the form by Showing above url at the website, this mean that the user data is not hidden, which may cause spaming.
- In viwes.py code we use this get method in 2 ways 1st one is:
n1= int(request.GET['num1'])

  n2 = int(request.GET['num2'])

- 2nd one is:
n1 = int(request.GET.get('num1'))

n2 = int(request.GET.get('num2'))

# ================8th day================
## Post Method With CSRF Token

- Use class of post in form and CSRF TOKEN like this:
- In form template page code post in small letters.
    - <form method="post">

    {% csrf_token %}

- crsf is used for hacker term., When hacker try to hit the user info form by thier internaly resources.
- Csrf token used to stop the spaming.

So, this thing is clear that if we use csrf token in our website then hacker not able to spaming your site.

    - Like GET method same doing all this Post method. Here, Post should be capital in request.
       -         if request.method=="POST":
            
            n1 = int(request.POST.get('num1'))

            n2 = int(request.POST.get('num2'))

## Page redirect in Django
 For this purpose we use this in view.py code. 1 way is used **HttpResponseRedirect**.
 - from django.http import HttpResponseRedirect

 when you send response the use the HttpResponseRedirect.
      - url= "/services/?output={}".format(finalAns)

            return HttpResponseRedirect(url)

 If you don't want to use this method, then use this **redirect**. 
 - from django.shortcuts import render, redirect.
   - when you send response the use the redirect.
      - url= "/services/?output={}".format(finalAns)

            return redirect(url)

## Form action in Django
By using action we submit the form to the other url, and we call the another view function at these url.
- Basically we use action when we want to immplement our logic at the other page,on the user form so we get the user form data then we Implement our logic at the page.
- We use action in form, Because action is the form attribute.
- we use action in form tag like this:
   - <form method="post" action="{% url 'submitform' %}">
   whichh url we pass there the data is send to this url which is passed.

   # ================9th day================
## Django Forms tutorial
- First we import **forms** from django, in forms.py which is created in the main project file, here we create forms.py in MyWebsite directory, where we inheret the import forms in user define class which name i keep myForm.
- Then in views.py code we import our created forms.py like this: **from .forms import myForm**.Then myform store in the veriable fn = myForm, then this variable is use as value with any key in this we use form key,
so, this key is we use in our userform.html like this:**{{form}}**
- Visit this site for more clerification of form:
   - https://www.djangoproject.com/

- To label the input field weuse this code like this in created forms.py
   - num1 = forms.CharField(label="value 1")
- If we want required or not required the input fields then we do this thing:
   - num1 = forms.CharField(label="value 1" required=False)
- If you want to change the type then use widget like this:
  - num1 = forms.CharField(label="value 1", required=False, widgets=forms.TextInput(attrs={'class':"form-control"}))

## Django calculator
## Check Even Odd and Number Using HTML Forms in Django
# ================10th day================
# Create Simple Marksheet in Django
# Normal Form Validation
# Models in your Django Application
When client request to to develop the website then if you make the website static, then if developers need to change any thing in website manually for this purpose you grant the menu in admin section where he able to change. SO, FOR this purpose we make the models in admin to show the option in admin to developer.
- In models we set the fields name, which relate thier database column.
- we keep model name same as table names.
- when we create models we need to mention the fields relate to model.
- We make models to make website things dynamic.
- **Visit the django model document official site**.

**We need to make model this 3 things**
    - Should be able to make model.
    - Should be able to convert model in migration.
    - and at the last how to migrate.

- Then after this doing above 3 things in admin option is appear.
- Model make command is this:
   **python manage.py startapp service**
   - above we create service name model.
- By pass this above command the service name folder is create in project directory.
   - In this folder we see the **models.py , admin.py** file in admin.py file we create logic in which we decide which field to be show to admin.

- when we make fileds in models we run this command.
   - **python manage.py makemigration**
- After run above command we run this below command which make the table.
   - **python manage.py migrate**
# ================11th day================
## 1) Create Model in Django
- 1st create app(by making app mean service option we get in admin)
- 2nd after creating model create fields
- 3rd set the migration
- 4rth then migrate model which create the tale in **DB**.
       - - **python manage.py startapp service**
      - To create model 1st we make app by ABove command then in 

models.py we make class with any name in our case we make service 

class and int the parameter we inherit the (models.Model) which crate the 

fields in model.
- Visit **Djangoproject.com/django.Charfield**.
- By using the djano fields we make schema.
- when migration is create it automatically create the **id key** and also 

auto set increment.
- Go in settings.py and then in **INSTALLED_APPS =** connect your app. 

in our case we connect the servicefile.

### 2) Now we need to run migration by this command:
  - **python manage.py makemigrations**.
  - After creating models we convert models in tables by migrate 

command.
      - **python manage.py migrate**
 - After once migrate again not able to migrate by the same above 

command.
   #### Register your models. here.
- Now go in **admin.py** code which is present in service app, we need 

to create some functions,keys, and some things to registerd then we able 

to see the option in admin.
    - In admin.py code import your model by this command.
    -  **from service.models import Service**.
- Now check in the admin option is not created or not.

- NOw i clear and summarize in how many fiels i work.
   - Create models in Fields **>>** By using make migration command 

convert model in migration **>>* Then go in settings.py where we 

connect our app in (INSTALLED APP)  **>>** then in admin.py code 

import model and make class and register model. **>>* then By using 

migrate command convert model in migrate **>>**

## Get all table data in Django | objects.all ()
- 1st in MyWebsite>>Views.py  we called the models.
   - from service.models import Service(the data is present in model, and data is goes in table.)
- Through model we get data.
   - we create the serviceData variable and write query to get all objects data.
      - Query is (**servicesData= Service.objects.all()**)
- Then make this key **servicesData** in **data** dictionary renderin Html page.
- Then at the service Html page we start the loop like this
   - {% for n in servicesData %}
   - {% endfor %}
and get the data.
- Here, like all() function thiere is many function we can used like (**get**(for single row),**filter**(for searching)).
## Django Order_by or Query set, Ascendingor and Desending
- 1st in MyWebsite>>views.py in quey we use order_by and in parameter we pass the field name.
    - servicesData= Service.objects.all().order_by('service_title') . mean ascending
- if this (-) before column name mean descending
             -servicesData= Service.objects.all().order_by('-service_title')
order without (-) mean ascending.
## Limit Query results in Django
We set the limit by slicing formula like [:3]<br>
We apply the slicing query on Objects query like this,<br>
servicesData= Service.objects.all().order_by('-service_title')[:3],[4:7]
- Don't use negative range like this [-1:6],[-3:-6] it gives error.
## Implementation and Logics of Custom Template filters in Django
Use **Safe** filter in the query which execute the tag which is used in the String paragraph or Text tag.<br>
Like this (**{{n.service_des | safe}}**),
(**{{n.service_des | upper | safe}}**),
(**{{n.service_des | lower}}**),
(**{{n.service_des | first| safe}}**)
- **Visit docs.djangoproject.com**  for more Template filters
## TinyMCE Integration With News App in Django
- See official site of
     - **pypi.org/project/django-tinymce/**
- 1st you install (**pip install django-tinymce**)
- Then in **2nd step** connect tinymce in settings.py>>INSTALLED_APPS

   - Then **new** name app is create, in new app go in models.py create class and inherit the models.Models.
- Go at official website **pypi.org/project/django-tinymce/**
    - and import **from tinymce.models import HTMLField**
- Then add **news** in settings.py
- Then go in news>> **admin.py** and import (**from news.models import news**)
- Then make class to show which field to show in admin site.
-  At last register your app like this (**admin.site.register(News,NewsAdmin**)
- And run this command(**python manage.py makemigrations**) in terminal to migrations.
- After migrations run this command in terminal(**python manage.py migrate**)
## Marquee Tag for Display News in Django
1st we add the new in  admin pannel, for this we use just Dummy content like we search on goole **Lorem IPsum** then copy title and discription and paste in news admin panel.

- Then after adding news, at the bottom of slider we run the Marquee.
    - If you know **j.query** then download plugging data.
- Then use **marquee** Tag in home html page.
- In Html for space we use this key word **&nbsp**
- To add the anchor tag we use like this:
   - (<a href=""> {{news.news_title}} </a>)
- Then we use the javascript event **overmouse="stop()"       overmouse="start()" **.
## Display news in Detail Page
- 1st we make the function in **views.py**:
   - Like: **def newsDetails(request,id):**

        - **return render(request,'newsdetails.html')**
- 2nd create the html file **newsdetails.html** then, create the urls in **urls.py** like :
    - path('newsDetails/<id>',views.newsDetails)

- Then go in **views.py** their in **newsDetails** function you make  **newsDetails**like :
      - newsDetails=News.objects.get(id=newsid)
      - Here, **get()** function use to carry the single row. Mean that we apply here condition which take only one row.

- Then we create the **data** dictinory in **newsdetails** function. and render this data varible in html page.
- In **newsdetails.html** page we dynamic the database data discription title and description.
- And we use **| safe** to execute the tags in database description.
## Reset Django Admin password
To reset/ change the password we must know the user name we see our user name in **sqlite** database.
- W e run this command **python manage.py changepassword admin**  here,

admin is user name so, user name is according to which you want to change.
## Explain Filter Work in Django
- 1st we create the **form** in service.py in form we create 1 text box and other is submit button.
- like this:
  - <form method="get">
              - <input type="text" name="servicename" value="" />
              - <input type="submit" value="Search"/>
  - </form>
- Now we search the data on the basis of title, we can search data in two ways like we can search data with full name or we can with the just first letter we use the database method of **like** keyword.
- Then we go in service.py in service function we create varible and call all objects,and apply condition.
     - use if statement and also apply inside if condition.
     -  In second if condition in **filter** parenthesis we use the
    ### ( __icontains)
  - ** __icontains** by this keyword we can search the title in  search bar by just **single word**
- And we create **data** dictionary and renderd in service.html page.

- **NOTE:** if you want to search with full name then use just this **(filter(service_title=st)** in function and if you want to search with just single alphabet then use this **filter(service_title__icontains=st)**.
- And if we not found the recoard then we use the Django template built in function **{% Empty %}**.
- **{% Empty %}** is work like **else**.
    
## Auto SlugField - Explained with Examples
- 1st we installed this in terminal by this command
    - Visit the official site (pip install django-autoslug)
    -  **pip install django-autoslug**
    -  we don't need to write the slug it automatically generate.
- Then import the AutoslugField.like this:
    **from autoslug import AutoSlugField**  in new.py **>> models.py**.
    - Then write this line of code:
    - **news_slug =AutoSlugField.(populate_from="news_title",unique=True,null=True,default=None)**
    - here, (populate_from="news_title") use for -->  for which **field** you want to make slug
    - this, unique=True use for -->  slug must be unique not repeated
    - this, null=True use for -->  slug may be **blank**.
    - this, default=None use for -->  defaulty carry may be null
- Then run this coomand in terminal **python manage.py makemigrations**
- after makemigrations run this command **python manage.py migrate**.

- **NOTE:** INSTALL autoSulgField >> make field in model >> import AutoslugField from autoslug >> then use for attribute (populate_from,unique,null,default)
## Pagination and How to Add Pagination in django
for example:  you have10, to 20 records, and you want to show just 2 records at a time and show the next, previous button which show the recoards. so, we use the **Paginators**.
- Visit the official Pagination in django website.
- In **Views.py** import this library
     - **from django.core.paginator import Paginator**
- Then apply logic on **views.py**
- In service function we crate the variable and in paginator function we pass to **parameters 1** at which object paginator is apply an **2nd parameter** is that how many data at a time should be display.
- Then get the page no, default value of page no is 1.
-  To get the page no we make variable **page_number**  here, we sent the page name url (**page_no= request.GET.get('page')**).
-  Now we want to know at the current time i'm stand at which page no, 
    - write this line of code: (**ServiceDataFinal= paginator.get_page(page_no)**).
    - Then make the data name dictinory and render in html page.
- Then go to work on Template 
  - In service.html file
  - Search on google **BOOTStraps Pagination 4** to make to make good looking.
  - Then copy the design and pass in htmlfile.

Then in copy design code pagination make some changes make first button and also set the url **?services/?page=1**.
- Then apply for if condition in copy pagination design code.
- if of first and previous is work only that time if previous r 1st page number is available.
   if contion is:  **{% if servicesData.has_previous %}**.and also close the if condition ** {% endif %}**

- Then apply previous buttoon logic if previousoage number is present then it take you to the previous page.
   - **href=/services/?page={{servicesData.previous_page_number}}**  previous_page_number syntax is fix you can't be change it.
- Then apply the logic on next button, same as previous but changing the next word with preivous word.
  - **href="/services/?page={{servicesData.next _page_number}}"**
  - The, apply the if condition on next button, beacuse next button is wait for next page so, at the last page we want to stop. so, we apply if condition to stop.
      - **{% if servicesData.has_next %}** and also close the if condition ** {% endif %}**
## Explain Last page Pagination & Number Counter Logic in Django
- Make the last page button andy apply logic in **views.py** service function dictionary and pass the created variable in **href** of last button. 
- Now we make the list number of pages in conprehensive way so, we make list comprehenstion.
  - For this list purpose we make the key **totalPagelist** in data dictionary of service function. 
  - Then start the loop below the previous button code.
  **{% for n in totalPagelist %}**.

- **NOTE:** just remember the syntax, **has_previous, previous_page_number, next_page_number,  has_next**
## Save Form Data to database
In this we take the data from front end and save the dasta in database.
- 1st we create the **app** with the name of **contactenquiry**. 
- It work like insert query.
- we work on **contact.htlm** we apply the **csrf_token** it's used when we use the **get method**.  
- Ans in **views.py** we make the **safeEnquiry** function and render in contact.html page.
- Then make url path in **url.py**.
- Then go in **view.py** and call the **contactEnquiry** model.
- Then in **saveEnquiry function** we recive the data from front end recive data. By appliying if condition.
- Now, make the variable with any name which you want then, in varible call the model **contactEnquiry()** which you create.
and pass the field name as a parameter.
   - At **right** side field name and **left** side value which you get.
- Then, which variable you use in our this case we use **en** variable then store the data of **en** variable like this.
    - **en.save()**
- Then, if you want to send **Response** then at the above of **if** condition make variable.
   - LIke, **n=''**
   - And at the below of **en.save** print message **n='Data Inserted.'**
   - Then, renderd this like this, **{'n':n}**.

## How to Upload a File with FileField() in Django(in admin side)
- Make **media** name folder in main project directory.
- Then go in **setting.py** and define 2 things 
   - 1 is: **MEDIA_ROOT= BASE_DIR /"media"** # here we conceret the (/"media")
   - 2nd is: **MEDIA_URL= "/media/"**
- Then, go in urls.py** import 2 library ** from Django.
   - **from django.conf import settings** (from this setting we use media)
   - **from django.conf.urls.static import static** (it allow to use media with URL_PATTERN **urls.py**)
- Then at the below of **urls.py** code use **DEBUG** code.( in this image and folder are store)
- Then, go in your APP in our case go in **news** app >> models.py >> make field **new_image** in which we use the **FileField()** functions. 
   - in FileField() parameter we declared the where upload the file.,
   - max_length,  (how much length of url)
   - null = True,
   - default = None
- **Note**: settings.py >> urls.py >> news model(your model)
- Then, makemigration the model. so, new field is show in admin side.
- Then, migrate the field.
- Then, go in **admin.py** wher we set the logic to show the name of image in admin.
## How to Display Uploaded Image in the Template in Django
- To display the image at the front end we use **<img>** tag.
- When we click on the slider urls at front page then which page is open the **title and description ** are show we want to show the image so, 
- We go in html page and use the **<img>** tag.
  - Write the code in html. file in which we give the folder name url to **src=** like this:
     -  <div class="col-12">
        <img src="/media/{{newsDetails.news_image}}"/>
    </div>
     - Here, **col-12** take the 12 coloum space.
- Now if you want to show the image one side and text other sidee then do this line of like this:
     -Then, divide the column in equal parts. both content and immage.
- Now, we want in which field we dont add the broken-image it Does not show the image sign. so, for this purpose we use the **if condition**.
## How to sending Email & (SMPT)simple made transfer protocol Setup  in Django Project
- We use the gmail **SMTP** in local system because currently we don't upload the **website**.
- Then open those your **gmail** account which you know the password and then **CLICK** on the 3,3 vertical rows in gmail account then, **click** on the **account*..
   - Then, search the **less secure app access** and allow.
- Visit the official websiteof django documentetion of **SMPT backEnd**
  - **https://docs.djangoproject.com/en/3.2/topics/email/**
- Then, go in **settings.py** and set this 5 things,
   - EMAIL_HOST = 'smtp.gmail.com'
   - EMAIL_PORT = 587
   - EMAIL_HOST_USER= 'khanammaryam036@gmail.com'
   - EMAIL_HOST_PASSWORD = 'mimibyby'
   - EMAIL_USE_TLS= True # it is a status which we give always True
- Then, use this library (**from django.core.mail import send_mail**) in **views.py**
  - ANd also **paste** the code in  which is copy from the official site.
    - And then, make changes according to your mails.
- Then open your template/ frontend page where we use the mail.setup code.
- **NOTE:** mail recive maybe late beacusewe use to send mail from over local system.

- **MAIN POINT**: create gmail >>>  go gmail and allow the less secure app    >>>   then make SMTP and then implent the all parrameter in settings.py   >>>   import libray and use code from **django official website**.  
   
## Explain HTML Content and what is Email Multi alternatives
- **NOTE** : Use **SMTP** in both when we use 
    - if i use send message
    - or if we use EmailMultiAlternatives
   - in both cases use **SMTP**.
- Use to send the **html tags** we use this Email Multi alternatives.
- In this all things are same as we use in local system gmail work, like **subject, True, content/message, from, To**.
- Int his also mention the which type of data mean (html) tag data send.
- Then we import this library (**from django.core.mail import EmailMultiAlternatives**) in **views.py**. and apply the logic.

