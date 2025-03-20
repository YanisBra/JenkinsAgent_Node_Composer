Documentation of the base image : https://hub.docker.com/r/jenkins/inbound-agent

docker build . -t jenkins_agent_react

Docker run --name jenkins_agent_react_container --init jenkins_agent_react -url http://<IPAdresse_of_jenkins_master>:8080 <password> <node_name>

To get the <IPAdresse_of_jenkins_master>, make this command :
docker inspect jenkins_master_container

<password> and <node_name> are given by the jenkins_master when you create a node

<!-- Pour moi : "docker run --name jenkins_agent_react_container --init jenkins_agent_react -url http://172.17.0.3:8080 aecf23eeac8604f346b225ae25fc83651f82a05215c28425d26add6109421d03 JenkinsAgent_Node" -->
