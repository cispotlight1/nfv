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
    stage('Docker Login') {
      steps {
        sh 'docker login -u=cispotlight -p=Ravadijay@801'
      }
    }
    stage('Docker Build') {
      steps {
        sh 'mvn package docker:build'
      }
    }
    stage('Docker Push') {
      steps {
        sh '''docker tag cispotlight/nfv-demo:latest cispotlight/nfv-demo:1.0.${BUILD_NUMBER}
docker push cispotlight/nfv-demo:latest
docker push cispotlight/nfv-demo:1.0.${BUILD_NUMBER}'''
      }
    }
  }
}