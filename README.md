# 'How To integrate REACT and DJANGo'
# 'REACT for front end development'
# 'DJANGO for backend development'

# step1
open cmd and create a django project 
### django-admin startproject project_name
now
### cd project_name

### npx create-react-app react_app

### npm run build

now open djano app settings.py and add the build folder into the DIRS inside TEMPLATE area. this will let the django know about the index.html file created after 'npm run build'

### os.path.join(BASE_DIR ,'react_app/build')

now open urls.py file and import TemplateView

### from django.views.generic import TemplateView

and add the below line inside the urlpatterns after ,

### path('',TempalteView.as_view(template_name='index.html')),


after that come back to settings.py and add the static folder so that django know about the css files and js files and other static files 

go to settings.py and scroll at the bottom to STATIC_URL

after it add 

### STATICFILES_DIRS=[ os.path.join(BASE_DIR,'reactapp/build/static'), ]

go to parent directory where the django file is created to run server

### python mange.py runserver

and you will see the react logo in your //localhost:8000 