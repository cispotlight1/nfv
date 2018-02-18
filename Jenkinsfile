pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        sh 'sudo mvn clean install -DskipTests'
      }
    }
    stage('Docker') {
      steps {
        sh 'sudo docker login -u=cispotlight -p=Ravadijay@801'
      }
    }
  }
}