# djangooauth

Small application having django and oauth integrated.

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

**Configure OAuth**

Navigate to url http://127.0.0.1/admin. Login with super users credentials created above.  Navigate to 'DJANGO AUTH TOOLKIT' add 'Applications'.

Settings are as follows:

  ***Client type: Confidential***<br>
  ***Authorization grant type: Resource owner password-based***<br>
  ***Name: Whatever you want.***<br>
    
Keep CLIENT_ID and CLIENT_SECRET, which need to be added to the code. 

Use below APIs to test the integration is working as expected.

**Test APIs**

Register user

       curl -d "username=halfspring&password=1234abcd" "127.0.0.1:8000/authentication/register/"
       
Customer APIs

Add customer

       curl -H "Authorization: Bearer <token>" -d "name=django&address=234/34&email=test@mail.com" 127.0.0.1:8000/v1/customer/
    
List customer

       curl -H "Authorization: Bearer <token>" 127.0.0.1:8000/v1/customer/
