# Autodeployment v2

- Add a github ci-action which builds the docker-image and deploys it on ghci.io.   
The last step of the github-workflow must be to deploy the project on the production server.  
- Add this deploy-script as a submodule: https://gist.github.com/timble-one/0cf1d8ef20f45662cfc31f5e894e9a8d  
- Make sure these make-targets exist in this project:
  - `make pull-prod`: must pull fresh docker-images
  - `make prod`: must recreate containers with the newest available images that are locally available
  - `make update`: normally just `pull-prod` + `prod`
- For the production-deployment, the github-workflow must use appleboy/ssh-action and only pass `host` and `username` as github-variable and the `key` as github-secret to the ssh-action.  
- The ssh-connection will automatically trigger the deployment-script on the production-server. The script does not have to be called explicitly from the github-workflow.  
