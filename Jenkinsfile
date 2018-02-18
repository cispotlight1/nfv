pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install -DskipTests'
      }
    }
    stage('Docker') {
      steps {
        sh 'docker login -u=cispotlight -p=Ravadijay@801'
      }
    }
  }
}