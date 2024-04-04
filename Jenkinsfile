pipeline {
  agent any
  tools { 
      maven 'maven3.9.6' 
      jdk 'jdk1.8.0' 
  }
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/candicez03/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('start bisect') {
      steps {
        sh 'git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
      }
    }

    stage('run bisect') {
      steps {
        sh 'git bisect run mvn clean test'
      }
    }

    stage('cleanup bisect') {
      steps {
        sh 'git bisect rest'
      }
    }

  }
}
