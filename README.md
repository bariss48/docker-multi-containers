# docker-multi-containers deploy to AWS
### Clone repository
```
$ git clone https://github.com/bariss48/docker-multi-containers.git
```
### Firstly you need a image , you can use my images on dockerhub. 
```
https://hub.docker.com/repository/docker/baris48/multi-containers-server
https://hub.docker.com/repository/docker/baris48/multi-containers-worker
https://hub.docker.com/repository/docker/baris48/multi-containers-nginx
https://hub.docker.com/repository/docker/baris48/multi-containers-client
```

### you need create VPC on AWS , for communication with others services. ( like AWS elastic cache , AWS relational database service )

### you need create a Elastic beanstalk , EC , RDS with AWS platform.

### then you must configure your services , (PGDATABASE, PGHOST, PGPASSWORD, PGPORT, PGUSER, REDIS_HOST, REDIS_PORT) add enviroment variables.

### then you must create secret key with AWS like ${{ secrets.AWS_ACCESS_KEY }} ${{ secrets.AWS_SECRET_KEY }}

### after all setup , you need to github Actions for deployment so create a .github directory and create a workflow directory inside , lastly create a deploy.yml inside.

```
$ touch deploy.yml   (/.github/workflow/deploy.yml)
```