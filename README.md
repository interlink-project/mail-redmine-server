# mail and redmine servers





To start your compose project, simply run the Docker Compose up command

The proxy service is inside redmine-docker-compose.yml keep in mind that without it, mail-docker-compose.yml won't be accessible

docker-compose -p redmine -f redmine-docker-compose.yml up -d
docker-compose -p mailu -f mail-docker-compose.yml up -d

Before you can use Mailu, you must create the primary administrator user account. This should be admin@interlink-project.eu. Use the following command, changing PASSWORD to your liking:

docker-compose -p mailu exec admin flask mailu admin admin interlink-project.eu PASSWORD

Login to the admin interface to change the password for a safe one, at one of the hostnames mail.interlink-project.eu/admin. Also, choose the "Update password" option in the left menu.


Create user:

docker-compose -p mailu exec admin flask mailu user test test@mail.interlink-project.eu 'test'
