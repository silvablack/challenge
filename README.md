# Challenge Reclame Aqui #

## The project is defined in three microservices, are them: ##

1. Service of Complaints to retreive information about complaints in data storage
2. Service of Company to retreive information about companies in data storage
3. Service of Report to retreive information about complaints by company in determined city

## The services were built with the following technology: ##

1. **Complains**
   + **Git Repository**: [Github](https://github.com/silvablack/service_complains)
   + **Docker Repository**: [Dockerhub](https://hub.docker.com/r/silvablack/service_complains/)
   + **Data storage:** [MongoDB](https://www.mongodb.com/)
   + **Programming Language:** [Nodejs](https://nodejs.org/en/) - [express](http://expressjs.com/pt-br/)
   + **Cache:** [Redis](https://redis.io/)

2. **Company**
   + **Git Repository**: [Github](https://github.com/silvablack/service_company)
   + **Docker Repository**: [Dockerhub](https://hub.docker.com/r/silvablack/service_company/)
   + **Data storage:** [MongoDB](https://www.mongodb.com/)
   + **Programming Language:** [Nodejs](https://nodejs.org/en/) - [express](http://expressjs.com/pt-br/)
   + **Cache:** [Redis](https://redis.io/)

3. **Report**
   + **Git Repository**: [Github](https://github.com/silvablack/service_report)
   + **Docker Repository**: [Dockerhub](https://hub.docker.com/r/silvablack/service_report/)
   + **Programming Language:** [Python](https://www.python.org/) - [Flask](http://flask.pocoo.org/)
   + **Data:** Connect in Complaints and Companies Data Storage

The services are hosted in [AWS](https://aws.amazon.com/pt/), [Mongo Atlas](https://www.mongodb.com/cloud/atlas) and [Redis Cloud](https://redislabs.com/)

+ **Public DNS:** ec2-18-223-203-222.us-east-2.compute.amazonaws.com
+ **IP:** 18.223.203.222
+ **Complains repository URI:** 666829565535.dkr.ecr.us-east-2.amazonaws.com/aws-ecr-api-complains
+ **Company repository URI:** 666829565535.dkr.ecr.us-east-2.amazonaws.com/aws-ecr-api-company
+ **Report repository URI:** 666829565535.dkr.ecr.us-east-2.amazonaws.com/aws-ecr-api-report

**PORT EXPOSED**

+ 5000 - **Complains**
+ 5010 - **Company**
+ 5020 - **Report**

All services are allocated in [Docker](https://www.docker.com/) containers

Each service contains Dockerfile to development and test environment
 
+ ./Dockerfile
+ ./Dockerfile-test

Each service contains Jenkinsfile with Pipeline to Deploy application and push to repository AWS ECR 
   
+ ./Jenkinsfile

### Environment ###


        /bash cat .env

+ URL\_SERVICE_COMPLAINS *(eg: 127.0.0.0)*
+ PORT\_SERVICE_COMPLAINS *(eg: 5000)*
+ URI\_DATA_COMPLAINS *(eg: USER:PASSWORD@cluster-shard-00-00-uzq97.mongodb.net:27017)*
+ URI\_CACHE_COMPLAINS *(eg: redis-16230.c16.us-east-1-3.ec2.cloud.redislabs.com:16230)*
+ PASSWORD\_CACHE_COMPLAINS *(eg: 1234)*
+ URL\_SERVICE_COMPANY *(eg: 127.0.0.0)*
+ PORT\_SERVICE_COMPANY *(eg: 5010)*
+ URI\_DATA_COMPANY *(eg: USER:PASSWORD@cluster-shard-00-00-uzq97.mongodb.net:27017)*
+ URI\_CACHE_COMPANY *(eg: redis-16230.c16.us-east-1-3.ec2.cloud.redislabs.com:16230)*
+ PASSWORD\_CACHE_COMPANY *(eg: 1234)*
+ URL\_SERVICE_REPORT *(eg: 127.0.0.1)*
+ PORT\_SERVICE_REPORT *(eg: 5020)*

### Setup ###
+ Clone:

        git clone git@github.com:silvablack/challenge.git

+ Build and run

        docker-compose -f FILE build
        docker-compose -f FILE up

to compose each app

+ FILE **./docker-compose.yml** to run all applications
+ FILE **./docker-compose.test.complains.yml** to test only complaints
+ FILE **./docker-compose.test.company.yml** to test only company
+ FILE **./docker-compose.test.report.yml** to test only report


API Documentation *HTML*

+ [Report API Documentation](https://documenter.getpostman.com/view/5097449/RWaGVA8g)
+ [Complains API Documentation](https://documenter.getpostman.com/view/5097449/RWToPHhM)
+ [Company API Documentation](https://documenter.getpostman.com/view/5097449/RWToPHhL)

API Documentation *JSON*

+ ComplainsAPI.json

+ CompanyAPI.json

+ ReportAPI.json
