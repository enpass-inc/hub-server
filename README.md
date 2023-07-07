# Enpass Hub Server Deployment #

This project offers example configurations for Docker Compose and Nginx, enabling you to set up a Enpass Hub Server with an Nginx reverse proxy quickly. 

## Usage ##

Clone the repository: ``` git clone https://github.com/enpass-inc/hub-server ```

1. Navigate to the examples/docker-compose directory.
2. Customize the ``` .env ``` and ``` docker-compose.yml ``` files to suit your application's needs. Update
the services, ports, volumes, environment variables, etc.
3. Modify the ``` nginx/nginx.conf ``` file to define the reverse proxy rules if required. 
4. Run the Docker Compose command to start the application: docker-compose up -d
5. Access your application through the ``` http://yourdomain.tld/ ```

Note: By default, the service is only available on HTTP port. Uncomment and set the appropriate variables to enable HTTPS in ``` .env ```, ``` docker-compose.yml ``` and ``` nginx.conf ```.

To access more detailed instructions, please refer to the documentation - https://www.enpass.io/deploy-hub-server