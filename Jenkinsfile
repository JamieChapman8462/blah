pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        lock(resource: "lock_${env.NODE_NAME}_${env.BRANCH_NAME}", inversePrecedence: true) {
          sleep 30
          milestone 1
          sh "echo Hello world"
        }
      }
    }
  }
}