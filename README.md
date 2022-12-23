# Code check module
https://codechecker.app/checker/londonappdev/start/recipe-app-api-2/s-10-setup-django-admin-04-support-modifying-users/

# recipe-app-api
Recipe api detail

Setup git account project
#
# add file requirements.txt
# add file Dockerfile
# add file .dockerignore
# create app folder

# Run below  command
docker build .

# add file docker-compose.yml

# Run below command
docker-compose build

# add file .flake8

# Run below command
docker-compose run --rm app sh -c "flake8"

# add django project via below command
docker-compose run --rm app sh -c "django-admin startproject app ."

# Run local server via below command
docker-compose up

# Rebuild app
docker-compose down
docker-compose build

# Run Test cases command
docker-compose run --rm app sh -c "python manage.py test"

# Run special command
docker-compose run --rm app sh -c "python manage.py wait_for_db"
docker-compose run --rm app sh -c "python manage.py wait_for_db && flake8"

# For Make migrations
docker-compose run --rm app sh -c "python manage.py makemigrations"
# for migrate
docker-compose run --rm app sh -c "python manage.py wait_for_db && python manage.py migrate"
# Docker volume space
docker volume ls
docker volume rm recipe-app-api_dev-db-data

# Cerate super admin
docker-compose run --rm app sh -c "python manage.py createsuperuser"


docker-compose run --rm app sh -c "python manage.py collectstatic"

docker-compose run --rm app sh -c "python -m pip install Pillow"
