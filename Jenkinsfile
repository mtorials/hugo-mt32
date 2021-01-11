pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'hugo'
      }
    }

    stage('deploy') {
      steps {
        sh '''mkdir /var/jenkins_home/userContent/mt32
cp static /var/jenkins_home/userContent/mt32'''
      }
    }

  }
}