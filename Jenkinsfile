pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'this is the nodejs build job'
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        echo 'this is the nodejs test job'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the nodejs package job'
        sh 'npm run package'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this nodejs pipeline has completed...'
    }

  }
}