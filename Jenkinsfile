pipeline {
  agent {
    docker {
      image 'docker'
      args '-v /var/run/docker.sock:/var/run/docker.sock'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t moderras/drone .'
      }
    }

  }
}
