pipeline {
  agent any
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
  }
  stages {
    stage('Run Terraform Code On Pipeline 1') {
      steps {
        git branch: 'main',
          credentialsId: '5b534ff6-d4a6-4744-a848-44359f12c7cb',
          url: 'https://github.com/ADCREW-LLC/khiem-dc11-terraform.git'
        sh "ls -lat"
        sh "terraform fmt"
        sh "terraform init -reconfigure -backend-config=\"aws_access_key_id=AKIAWIVUTCVPTL7HHOK3\" -backend-config=\"aws_secret_access_key=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\""
        sh "terraform validate && terraform plan"
      }
    }
  }
}

