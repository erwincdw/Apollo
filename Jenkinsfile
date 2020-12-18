pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/agileworks-tw/java-maven-junit-helloworld.git'
      }
    }

    stage('build') {
      steps {
        sh 'mvn clean package'
      }
    }

  }
}