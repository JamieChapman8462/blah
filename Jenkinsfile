pipeline {
  agent any
  stages {
    stage('checkout repository') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: 'refs/heads/develop']],
          doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs:
          [[credentialsId: '3535a10f-0df0-4f9d-bff7-c50bef95d944', url: 'git@github.com:JamieChapman8462/blah.git']]])
      }
    }
    stage('Build') {
      lock(resource: "lock_${env.NODE_NAME}_${env.BRANCH_NAME}", inversePrecedence: true) {
        steps {
          sleep 30
          milestone 1
          sh "echo Hello world"
        }
      }
    }
  }
}