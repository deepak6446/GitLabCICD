# GitLab CICD to deploy docker compose file to google app engine flexible.

Gitlab uses docker image to run every stage specified in the pipeline.</br>
For building a docker image we will have to run and build docker in a docker container.</br>
There are 3 approaches for this [here](https://docs.gitlab.com/ee/ci/docker/using_docker_build.html), I have used docker-in-docker (dind) image.</br>

# Steps to peform on GITLAB
##### Setting >> CICD
##### expand runners 
##### install runner on kubernets and enable it.

# How does it work 
whenever a code is pushed to repo the CICD starts as soon as it find <b>.gitlab-ci.yml</b> in the repo. </br>
Google app engine deploy's continer with the specified configurations <b>in app.yaml</b> </br>

It Gets env file from google storage, builds image using docker-compose, upload's the image to google registry.</br>
In deployment stage it gets image from docker registry, deploys the image to google image.
