# Jupyter + MongoDB

Includes example Jupyter notebook to push data to MongoDB, and a [mongo-express](https://github.com/mongo-express) admin interface. Runs the [Jupyter Data Science Notebook](https://hub.docker.com/r/jupyter/datascience-notebook/) container with an installation of [Zipline](https://github.com/quantopian/zipline).

## Instructions

1. Clone this repository and `cd` into the directory:

    `git clone https://github.com/aeksco/docker_jupyter_mongodb.git`

    `cd docker_jupyter_mongodb`

2. Start the docker containers:

    `docker-compose up`

    **NOTE** - there's a unique token you'll need to access the Jupyter notebook server.

    The docker-compose terminal will print out a self-authenticating URL, which looks like:

    `http://localhost:8888/?token=8a78623a6eadf3433f0b1ccef1049b2ce525fef20823a12d`

    Opening that URL will take you to the notebook server.

## Usage

- MongoDB admin interface running at [http://localhost:8081](http://localhost:8081)

- Jupyter server running at [http://localhost:8888](http://localhost:8888)

- Run the `MongoDB` notebook to create the `jupyter` database and a single example `restaurant` record

## Notes

- This configuration is not optimized for size. The `jupyter/datascience-notebook` has a footprint of 6.28 GB - you could substitute the `jupyter/minimal-notebook` (footprint of 2.74 GB) by changing the `FROM` statement in `jupyter/Dockerfile`.


## Optional NGINX Configuration
- Run the following to setup an NGINX reverse-proxy to the Jupyter Notebook server
  ```
  sudo apt-get update
  sudo apt-get install nginx
  ```

<!-- sudo nano /etc/nginx/sites-available/my_site
< PASTE ABOVE AND SAVE >
ln -s /etc/nginx/sites-available/my_site /etc/nginx/sites-enabled/my_site

sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx

Run install_c_kernel command as root user with docker-compose run
docker-compose run --user="root" jupyter install_c_kernel -->