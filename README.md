# CREATING A DJANGO PROJECT WITH docker-compose AND PostgreSQL
To get this to work I had too:
1. create Dockerfile/docker-compose.yml
	- the dockerfile cannot define the command/entry point
	- the docker-compose must include the start command (mange.py runserver)

2. had to create the django project inside of docker compose for some reason
	- docker-compose run web django-admin.py startproject postgresdjango . 
 	-  docker-compose run web python manage.py migrate 
		- for some reason I didn't have to makemigrations first
3. made super user to prove access to the database was successfull:
	-  docker-compose run web python manage.py createsuperuser
