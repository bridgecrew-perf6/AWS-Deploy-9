# Pipeline-process

- The pipeline porcess is integrated with circleci and it consist of 5 steps as listed below and all its commands are also listed in confiq.yml file in circleci folder and all these commands calls the long commands listed in package.json file in teh project root folder

1. Installing back end (API) dependencies using commmand `npm run backend:install` which consequesntly runs `cd udagram-api && npm install`   

2. Installing front end dependencies using commmand `npm run frontend:install` which consequesntly runs `cd udagram-frontend && npm install --force`   

3. Building the back end (API) using command `npm run backend:build` which consequesntly runs `cd udagram-api && npm run build`  

4. Building the front end using command `npm run frontend:build` which consequesntly runs `cd udagram-frontend && npm run build`  

5. Deploying the application using command `npm run frontend:deploy` which consequesntly runs `cd udagram-frontend && npm run deploy`  

