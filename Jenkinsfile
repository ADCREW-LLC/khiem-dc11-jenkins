//git branch: 'master',
//    credentialsId: '5b534ff6-d4a6-4744-a848-44359f12c7cb',
//    url: 'ssh://git@github.com:ADCREW-LLC/khiem-dc11-terraform.git'

pipeline {
  agent any
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
  }
  stages {
    stage('Set git credentials & repo') {
      steps {
        git branch: 'main',
          credentialsId: '5b534ff6-d4a6-4744-a848-44359f12c7cb',
          url: 'https://github.com/ADCREW-LLC/khiem-dc11-terraform.git'
        sh "ls -lat && pwd"
      }
    }

    stage('Checkout code') {
        steps {
            checkout scm
        }
    }
  }
}

