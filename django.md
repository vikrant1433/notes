http://ideavim.sourceforge.net/vim/editing.html
# creating a project
* `django-admin startproject mysite`
# creating an app
* `python manage.py startapp polls`


By running makemigrations, you’re telling Django that you’ve made some changes to your models (in this case, you’ve made new ones) and that you’d like the changes to be stored as a migration.

# migration
* python manage.py makemigrations <app-name>
*
