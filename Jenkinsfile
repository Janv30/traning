pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        sh 'pwd'
      }
    }

    stage('stage2') {
      parallel {
        stage('stage2') {
          steps {
            build(job: 'demo', wait: true, propagate: true, waitForStart: true)
          }
        }

        stage('') {
          steps {
            echo 'run pipeline successfully'
          }
        }

      }
    }

    stage('stage3') {
      steps {
        echo 'this is 3rd stage'
      }
    }

  }
}