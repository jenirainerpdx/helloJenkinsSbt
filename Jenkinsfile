pipeline {
  agent {
    label 'ecs-agent'
  }

  environment {
    DOCKER_IMAGE_TAG = "${BUILD_TAG}".toLowerCase()
  }

  stages {
    stage('Checkout code') {
        steps {
            echo 'Checking out code from SCM...'
            checkout scm
          }
     }

     stage('Build') {
           steps {
             echo 'Building project...'
             sh "${tool name: 'sbt', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt compile"
           }
         }
  }
}