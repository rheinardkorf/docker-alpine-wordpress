# docker-alpine-wordpress

This is a very basic WordPress setup using the super tiny Alpine Linux distribution and official Docker images for WordPress and PHP FPM.

## Installation

### Docker

To use this project you first need Docker installed. It would do you well to learn more about Docker, but these steps will get
you going fast. The first step of course is to get Docker. You can get Docker from here:  

* MacOS: https://www.docker.com/docker-mac  
* Windows: https://www.docker.com/docker-windows
* Other: https://www.docker.com/get-docker

Once Docker is installed you should be able to run the following from command line (terminal / cmd.exe):  `docker -v`. Congrats
and welcome to the awesome world of Docker.

### Setting up your site

Setting up a site is really easy. Go to any of your project folders and then run the following (replacing my-site with whatever you wish):  

```
git clone https://github.com/rheinardkorf/docker-alpine-wordpress.git my-site
cd my-site
docker-compose up -d
```

Note: The first time you run `docker-compose` it might take a while to download the Docker images.

This will spin up a few Docker containers:

* nginx - Which acts as a proxy for your site and the PHP FPM server.  
* wordpress - A PHP FPM flavor of the WordPress Docker image.  
* db - MySQL for serving your WordPress a database.  
* phpmyadmin - A web interface for your database.  

## URLs

The following URLs will now be available for your project:  

* http://localhost/ -- Your development WordPress site. (You will install WordPress upon first visit).
* http://localhost:8080/ -- The PHPMyAdmin interface for your database (username: root, password: root)

You can now use your development WordPress site as you would any WordPress site.  

## Project Folder Structure

Inside your primary `my-site` project folder you will see the following:  

* docker-compose.yml -- The Docker configuration for your project.  
* site.conf -- The nginx configuration for your site.  
* htdocs/ -- The WordPress files.  
* themes/ -- A mapping to the WordPress themes folder.
* plugins/ -- A mapping to the WordPress plugins folder.

## Stopping your project

Running the following will stop all active Docker containers: `docker stop $(docker ps -q)`

## Starting your project again

Make sure you are in your project folder (the one with docker-compose.yml) and run `docker-compose up -d`.

Simple.
