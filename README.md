# Enpass Hub Server Deployment #

This project offers example configurations for Docker Compose and Nginx, enabling you to set up a Enpass Hub Server with an Nginx reverse proxy quickly. 

## Usage ##

Clone the repository: ``` git clone https://github.com/enpass-inc/hub-server ```

1. Navigate to the examples/docker-compose directory.
2. Customize the ``` .env ``` and ``` docker-compose.yml ``` files to suit your application's needs. Update
the services, ports, volumes, environment variables, etc.
3. Enpass Hub supports docker compose secrets. Use environment variables with  ```_FILE``` suffix.
4. Modify the ``` nginx/nginx.conf ``` file to define the reverse proxy rules if required. 
5. To persist the database, create an extra volume with the command: ``` docker volume create --name=postgres_data ```
6. Run the Docker Compose command to start the application: ``` docker-compose up -d ```
7. Access your application through the ``` http://yourdomain.tld/authorise/create/admin/first/ ```

## Options ##

1. To persist postgres data in a local folder instead of a docker volume, comment/uncomment the relevant lines in ``` docker-compose.yml ```
2. If you are using an external nginx, it will need access to static files of the application. You can choose either of the following options: 
- Copy static files a local folder, comment/uncomment the relevant lines in ``` docker-compose.yml ```
- Set environment variable ``` HUB_STATIC_URL=https://hub-static.enpass.io/static/ ```, the static files will be served directly from our CDN.

Note: By default, the service is only available on HTTP port. Uncomment and set the appropriate variables to enable HTTPS in ``` .env ```, ``` docker-compose.yml ``` and ``` nginx.conf ```.

To access more detailed instructions, please refer to the documentation : https://www.enpass.io/deploy-hub-server
