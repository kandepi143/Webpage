pipeline {
  agent any
  stages {
    stage('SCM') {
      steps {
        git(url: 'https://github.com/kandepi143/Webpage.git', branch: 'master', poll: true)
      }
    }
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            tool(name: 'Maven', type: 'maven')
          }
        }
        stage('') {
          steps {
            sh 'mvn clean install'
          }
        }
      }
    }
  }
}