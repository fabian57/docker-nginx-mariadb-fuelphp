# Docker LEMP stack blueprint

Here LEMP stands for Linux Nginx MariaDB and FuelPHP


This repository contains nginx configuration files, two dockerfiles for php7-fpm, one being based on debian and the other on alpine, and a docker-compose file.

To use FuelPHP simply remove the app folder and run create your FuelPHP app,
```
rm -rf app
oil create app
cd app
oil refine install
```

or just keep the existing folder to use vanilla PHP 

To use the debian or alpine PHP image, simply change the docker-compose.yml file. For debian write docker\_builds/Dockerfile.phpfpm after dockerfile: for the phpfpm service and for alpine add -alpine at the end.

Finally, in the folder run
```
docker-compose up -d
```
Now check if the website is running by typing your machines IP in a browser (or your local address if your on linux).
You should see the PHP configuration, or the FuelPHP welcome page if you installed it.

If you want to shut it down, just type the following command in the folder
```
docker-compose down
```

Hope this helps and you can enjoy a dockerized LEMP app without going through too much trouble.

*Note: Not running in deamon mode seems to shut down MariaDB, so don't forget to add the -d flag* 

*This blueprint is based on the crashcourse at https://github.com/ucfopen/fuelphp-crash-course-docker.*
