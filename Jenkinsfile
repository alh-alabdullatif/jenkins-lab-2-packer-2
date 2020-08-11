pipeline {
  agent {
    docker {
      image "bryandollery/terraform-packer-aws-alpine"
      args "-u root"
    }
  }
  environment {
    CREDS = credentials('Alhanouf-aws-creds')
    AWS_ACCESS_KEY_ID = "$CREDS_USR"
    AWS_SECRET_ACCESS_KEY = "$CREDS_PSW"
    OWNER = 'alhanouf'
    PROJECT_NAME = 'web-server'
  } 
  stages {
    stage("build") {
      steps {
        sh 'packer build packer.json'
      }
    }
  }
}