pipeline {
  agent any

  environment {
    SCHOOL = "datascientest"
    NAME   = "Anthony"
  }

  stages {
    stage("Env Variables") {
      environment {
        NAME = "lewis"
        BUILD_ID = "2"
      }
      steps {
        echo "SCHOOL = ${env.SCHOOL}"
        echo "NAME = ${env.NAME}"
        echo "BUILD_ID = ${env.BUILD_ID}"

        script {
          env.SOMETHING = "1"
        }
        echo "SOMETHING = ${env.SOMETHING}"
      }
    }

    stage("Override Variables") {
      steps {
        script {
          env.SCHOOL = "I LOVE DATASCIENTEST!"   // wird NICHT überschreiben
          env.SOMETHING = "2"                   // wird überschreiben
        }

        echo "SCHOOL = ${env.SCHOOL}"
        echo "SOMETHING = ${env.SOMETHING}"

        withEnv(["SCHOOL=DEV UNIVERSITY"]) {
          echo "SCHOOL(withEnv) = ${env.SCHOOL}"
        }

        withEnv(["BUILD_ID=1"]) {
          echo "BUILD_ID(withEnv) = ${env.BUILD_ID}"
        }
      }
    }
  }
}
