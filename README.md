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
<img width="967" alt="Ekran Resmi 2022-03-23 13 19 47" src="https://user-images.githubusercontent.com/50153950/159677047-fb5fd063-f5ec-40dd-8818-cbcb0abc7a22.png">

### you need create VPC on AWS , for communication with others services. ( like AWS elastic cache , AWS relational database service )

### you need create a Elastic beanstalk , EC , RDS with AWS platform.

### then you must configure your services , (PGDATABASE, PGHOST, PGPASSWORD, PGPORT, PGUSER, REDIS_HOST, REDIS_PORT) add enviroment variables.

### then you must create secret key with AWS like ${{ secrets.AWS_ACCESS_KEY }} ${{ secrets.AWS_SECRET_KEY }}

### after all setup , you need to github Actions for deployment so create a .github directory and create a workflow directory inside , lastly create a deploy.yml inside.

```
$ touch deploy.yml   (/.github/workflow/deploy.yml)
```
### Architecture ( production )
<img width="816" alt="architecture" src="https://user-images.githubusercontent.com/50153950/159677182-8dc8dd87-fccb-4bf3-ba78-51927b7a938c.png">

### Architecture ( development )
<img width="800" alt="development" src="https://user-images.githubusercontent.com/50153950/159677298-7bbd85db-6498-48f3-aa46-cda2e65113ff.png">

### Architecture ( VPC )
<img width="667" alt="VPC" src="https://user-images.githubusercontent.com/50153950/159677663-07fa3633-f2a4-48c4-8f57-81f386457089.png">

#### After all this your beanstalk app status must be 'OK' 
<img width="899" alt="Ekran Resmi 2022-03-23 13 23 17" src="https://user-images.githubusercontent.com/50153950/159678133-fe8ff58a-8f0d-459c-a0d4-9b16e060304c.png">

### Finally you can see your deployment success: ( check URL )
<img width="1552" alt="Ekran Resmi 2022-03-23 13 24 41" src="https://user-images.githubusercontent.com/50153950/159678376-dcc0cbd0-a870-49a4-a570-4e7a4d1e1f8f.png">

## Reference
### Docker and Kubernetes: The Complete Guide ( Stephen Grider Course )
