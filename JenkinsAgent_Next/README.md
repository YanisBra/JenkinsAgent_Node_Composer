Documentation of the base image : https://hub.docker.com/r/jenkins/inbound-agent

docker build . -t jenkins_agent_next_docker

docker run --init --name jenkins_agent -v /var/run/docker.sock:/var/run/docker.sock jenkins-agent-with-docker
-url http://<Jenkins_master_IP_adress>:8080 <secret> <agent_name>

To get the <IPAdresse_of_jenkins_master>, make this command :
docker inspect jenkins_master_container

<password> and <node_name> are given by the jenkins_master when you create a node

<!-- Pour moi :  docker run --init --name jenkins_agent_next_docker_container -v /var/run/docker.sock:/var/run/docker.sock jenkins_agent_next_docker -url http://172.17.0.2:8080 ca7f77eb1d2045ca4673ade5bb7efc8c1d314830dcade6e7e2e9a00734fa8edb JenkinsAgent_next_docker -->
