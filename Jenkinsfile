pipeline {
  agent any

  environment {
    DOCKER_ID    = "mari990"
    DOCKER_IMAGE = "datascientestapi"
    DOCKER_TAG   = "v.${BUILD_ID}.0"
  }

  stages {
    stage('Docker Build') {
      steps {
        sh '''
          docker rm -f jenkins || true
          docker build -t $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG .
        '''
      }
    }

    stage('Docker Run') {
      steps {
        sh '''
          docker run -d -p 80:80 --name jenkins $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG
          sleep 5
        '''
      }
    }

    stage('Test API') {
      steps {
        sh '''
          curl localhost
        '''
      }
    }
  }
}
