pipeline {
  agent {
    docker {
        image 'jenkins_sandbox_agent:latest'
        args '-v /var/run/docker.sock:/var/run/docker.sock' 
    }
}

  tools{
    maven  "maven3.9"
    jdk "JDK_11"
  }

   environment {
        NEXUS_VERSION = "nexus3"
        SNAP_REPO = "vprofile-snapshot"
        NEXUS_USER = "admin"
        NEXUS_PASS = "1998"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "172.25.0.3:8081"
        NEXUS_REPOSITORY = "vprofile-release"
        CENTRAL_REPO = "vprofile-maven-centraL"
	      NEXUS_REPOGRP_ID    = "vprofile-maven-group"
        NEXUS_CREDENTIAL_ID = "nexuslogin"
    }

  stages{
    stage('Build'){
      steps {
        sh 'mvn -s settings.xml -DskipTests install'
      }
    }
  }

}
