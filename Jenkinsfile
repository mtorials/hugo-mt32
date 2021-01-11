pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'hugo'
        sh '''ls -a -l
hugo version'''
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