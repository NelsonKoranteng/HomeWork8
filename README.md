Clone the repository to get started:
Copied my Environment
Copied my previous project (myproject) into the Homework 8 folder:

bash
Copy code
cp -r myproject/* ../hw8
Made sure to update any directory names or paths accordingly.

Introduction to MVC and Templates
MVC (Model-View-Controller) is a design pattern that separates an application into three main components:

Setting Up a Template
1. Created a Template Folder
Inside the mycontactsapp directory, create a folder named templates:
mycontactsapp/templates/

3. Create index.html
Add the following content to a new file named index.html inside the templates folder:

Updated the View
Update the views.py file in mycontactsapp to use the index.html template:

python
Copy code
from django.shortcuts import render
from .models import Contact

Run the server:
python manage.py runserver
Visit http://localhost:8000/ and ensure the first contact's name is displayed.

Tasks to Complete
1. Display All Contacts Using a Loop
Add a for loop in index.html to dynamically display all contacts:

html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <title>My Contacts</title>
    {% load static %}
    <link rel="stylesheet" href="{% static 'styles.css' %}" />
</head>
<body>
    <h1>My Contacts</h1>
    <p>All contacts:</p>
    <ul>
        {% for contact in contacts %}
            <li>{{ contact.first_name }} {{ contact.last_name }}</li>
        {% endfor %}
    </ul>
</body>
</html>
2. Add More Contacts
Access the admin interface at http://localhost:8000/admin/.

Added several new contacts using the admin interface.
Refresh the website to verify all contacts are displayed dynamically.
3. Use Static Files
a. Create a static Directory
Create a static folder inside mycontactsapp:
mycontactsapp/static/
b. Add a CSS File
Created a file named styles.css inside the static folder:
mycontactsapp/static/styles.css
c. Load Static Files in the Template
Update the index.html file to include the CSS:
d. Update styles.css
Modified at least three CSS properties.

Final Verification
Run the server:

python manage.py runserver
Visit http://localhost:8000/ 
