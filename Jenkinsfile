pipeline {
  agent any

  environment {
    DOCKER_ID    = "mari990"
    DOCKER_IMAGE = "datascientestapi"
    DOCKER_TAG   = "v.${BUILD_ID}.0"
    SCHOOL       = "datascientest"
  }

  stages {
    stage("Env check") {
      steps {
        echo "SCHOOL = ${env.SCHOOL}"
        echo "DOCKER_ID = ${env.DOCKER_ID}"
        echo "DOCKER_IMAGE = ${env.DOCKER_IMAGE}"
        echo "DOCKER_TAG = ${env.DOCKER_TAG}"
        echo "BUILD_ID = ${env.BUILD_ID}"
        sh 'printenv | sort | head -n 30'
      }
    }
  }
}
