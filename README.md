# AWS Deployment Project

## Table of Contents  

* [Description](#description)   
* [Prequisites](#prequisites)    
* [Usage](#usage)     
* [Dependencies](#dependencies)         
* [AWS-hierarchy](#aws-hierarchy)   
* [Pipeline-process](#pipeline-process)   

## Description   

This is an **AWS Deployment Project** that uses prebuilt frontend website and nodejs API to deploy on AWS and it was built for a Udacity course. The front end website can be accessed using this link: [http://udagram-test-bucket-1.s3-website-us-east-1.amazonaws.com].  

## Prequisites 

Before using the project locally, user need to have postgreSQL, Nodejs and AWS CLI installled .   

## Usage  

1. To build the project, user need to install the dependencies listed in package.json file in the front end and api . just run `npm install` in your terminal in project directory of the frontend and the api to build the project with all dependencies listed in package.json file.     

2. To build the API, write the command `npm run build` in the terminal in the API root directory.     

3. To build the front ent, write the command `ng build` in the terminal in the front end directory.       

4. To run the API locally, run `npm run dev` in your terminal in API root directory. the server runs on host: **localhost:3000** 

5. To run the front end locally. run `ng serve` in your terminal in front end directory. the server runs on host: **localhost:4200**

## Dependencies   
- Postgresql
- Node 
- dotenv
- sequelize
- jsonwebtoken
- bcrypt
- typescript      

## AWS-hierarchy
- the AWS-hierarchy consists of 3 main services as listed below and there is an explaining diagram in the screenshots folder:

1. S3: which hosts the front end website in which users can enteract with the website.    

2. Elastic Beanstalk: which hosts the api of the project which the front end can communicate with it to retrieve data.    

3. RDS: which hosts the postgres database where the API can post and get data from.   

## Pipeline-process   

- The pipeline porcess is integrated with circleci and it consist of 5 steps as listed below and all its commands are also listed in confiq.yml file in circleci folder and all these commands calls the long commands listed in package.json file in teh project root folder

1. Installing back end (API) dependencies using commmand `npm run backend:install` which consequesntly runs `cd udagram-api && npm install`   

2. Installing front end dependencies using commmand `npm run frontend:install` which consequesntly runs `cd udagram-frontend && npm install --force`   

3. Building the back end (API) using command `npm run backend:build` which consequesntly runs `cd udagram-api && npm run build`  

4. Building the front end using command `npm run frontend:build` which consequesntly runs `cd udagram-frontend && npm run build`  

5. Deploying the application using command `npm run frontend:deploy` which consequesntly runs `cd udagram-frontend && npm run deploy`  

