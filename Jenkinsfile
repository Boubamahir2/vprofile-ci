pipeline {
  agent any
  
  tools{
    maven  "MAVEN3"
    jdk "OracleJDK"
  }


   environment {
        NEXUS_VERSION = "nexus3"
        SNAP_REPO = "vprofile-snapshot"
        NEXUS_USER = "admin"
        NEXUS_PASS = "1998"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "192.168.56.1:8081"
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
