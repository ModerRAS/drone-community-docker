pipeline {
  agent any
  triggers {
    cron('0 0 1 * *')
  }
  environment {
    DOCKERHUB_CREDENTIALS=credentials('7b99cc2b-e94e-4c8e-9779-fb26bbc8efdf')
  }

  stages {
    stage('Build') {
      steps {
        sh 'docker build -t moderras/drone .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push moderras/drone'
      }
    }
  }
}
