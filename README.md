# GitLab CICD to deploy docker compose file to google app engine flexible.

Gitlab uses docker image to run every stage specified in the pipeline.</br>
For building a docker image we will have to run and build docker in a docker container.</br>
There are 3 approaches for this [here](https://docs.gitlab.com/ee/ci/docker/using_docker_build.html), I have used docker-in-docker (dind) image.</br>

# Steps to peform on GITLAB
move to project repository
1. Setting > CICD
2. expand runners 
3. install runner on kubernets and enable it.

# How does it work 
1. CICD starts as soon as it find <b>.gitlab-ci.yml</b> in the repo. </br>
2. Google app engine deploy's container with the specified configurations in <b>app.yaml</b> </br>
3. It gets env file from google storage, builds image using docker-compose, upload's the image to google registry.</br>
4. In deployment stage it gets image from docker registry, deploys the image to google cloud run.
