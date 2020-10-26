# djangooauth

**Set up**

Run 

    pip install django django-rest-framework django-oauth-toolkit


After sucessfull install run django database mograrions

      python manage.py makemigrations
   
      python manage.py migrate

Create super user

       python manage.py createsuperuser

Start server

       python manage.py runserver

**Test APIs**

Register user

       curl -d "username=halfspring&password=1234abcd" "0.0.0.0:8000/authentication/register/"
       
Customer API

Add customer

       curl -H "Authorization: Bearer <token>" -d "name=django&email=test@mail.com" 0.0.0.0:8000/v1/customer/
    
List customer

       curl -H "Authorization: Bearer <token>" 0.0.0.0:8000/v1/customer/
