FROM jenkins/jenkins

USER root

RUN apt-get update &&\
 apt-get install -y docker.io &&\

# Add Docker's official GPG key:
 apt-get update &&\
 apt-get install ca-certificates curl &&\
 curl -fsSL https://download.docker.com/linux/jenkins/gpg -o /etc/apt/keyrings/docker.asc &&\
 chmod a+r /etc/apt/keyrings/docker.asc &&\

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  tee /etc/apt/sources.list.d/docker.list > /dev/null &&\
 apt-get update &&\
apt-get install docker-compose-plugin



RUN jenkins-plugin-cli --plugins git github github-branch-source pipeline-github \
                 git-client credentials credentials-binding \
                 workflow-aggregator job-dsl
