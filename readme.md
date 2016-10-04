Web application docker template
===============================

This is a template to create the environment for a web application
using nginx and php-fpm at its core.

It is intended to be used as a development environment, not for production.

It provides
-----------

* a php-fpm image
* a nginx image
* a mail catcher
* a image used as data-only container
* a docker-compose file to glue it all together

What it lacks
-----

There is no database image. But adding your favourite database
image to docker-compose should be easy. Useful images are:

* https://hub.docker.com/_/mysql/ (the official mysql image)
* https://hub.docker.com/_/mariadb/ (the official mariadb image)
* https://hub.docker.com/_/mongo/ (the official mongo db)

How to use it
--------------

1. Give your project a name: Edit the file *project_name_env.sh*. Then run `source ./project_name_env.sh`. (You can omit this if you want to use the name of the current directory as a project name).
2. Check *docker-compose.yml* if it  contains all you need, or if you want to add more containers.
3. Check the  nginx configuration, especially the server name. Add it to your */etc/hosts* file.
4. Put your application files in the *./project* directory, or remove it and symlink your
   existing app to this name. The document root is configured to be *./project/public/*. You
   can change it in the nginx config if you want.
5. Run (from the base directory) `docker-compose up -d` (this may take a while, as php will be
   compiled from source...

That's it. Have fun :-)

