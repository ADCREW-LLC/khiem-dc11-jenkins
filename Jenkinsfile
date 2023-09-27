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
        script {
           GIT_COMMIT_EMAIL = sh (
                script: 'git --no-pager show -s --format=\'%ae\'',
                returnStdout: true
            ).trim()
            echo "Git committer email: ${GIT_COMMIT_EMAIL}"
        }
        sh "terraform fmt"
        sh "terraform init -reconfigure"
        sh "terraform validate"
        sh "terraform plan"
        emailext body: 'Test Message',
          subject: 'Test Subject',
          to: GIT_COMMIT_EMAIL
      }
    }
  }
}

