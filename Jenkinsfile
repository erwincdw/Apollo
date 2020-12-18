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

    stage('archive') {
      parallel {
        stage('archive') {
          steps {
            archiveArtifacts 'target/*.jar'
          }
        }

        stage('report') {
          steps {
            junit '**/target/surefire-reports/TEST-*.xml'
          }
        }

      }
    }

  }
}