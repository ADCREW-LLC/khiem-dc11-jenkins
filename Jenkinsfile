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
        sh "export AWS_ACCESS_KEY_ID=AKIAWIVUTCVPTL7HHOK3 && export AWS_SECRET_ACCESS_KEY=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"
        sh "terraform fmt && terraform init && terraform validate"
      }
    }
  }
}

