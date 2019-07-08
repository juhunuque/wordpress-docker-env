# Wordpress local env - Dockerized

## Description
If you are looking a way to develop your Wordpress site without many complications, and you only need a local environment and start right away, here's what you need!

## How to use this?

### Pre-requisites
- Docker installed
- docker-compose installed

### Installation
For convenience, the environment is wrapped up with a docker-compose recipe, just go to the terminal and run:
```sh
docker-compose up -d
```

### Stop the service
If you want to release the resources assigned to the Wordpress stack, just go to the terminal and run:
```sh
docker-compose down 
```

If you to remove the current volumes as well, in the terminal run the following:
```sh
docker-compose down -v
```

It's recommended to remove the volume folder too:
```sh
rm -rf ./volume
```

## Details
* Within the /volume you will find the wp content folder, in case you want to modify something manually, for instance, install a theme manually.
* Inside the /wp you will see the uploads.ini file, there you can update the value of upload_max_filesize. If you want to verify the value you specified was applied, run in the terminal:
```sh
docker exec [CONTAINER_ID] php -i | grep upload
```