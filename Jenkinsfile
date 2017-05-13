#!groovy
node {
  stage('Get Repository'){
    checkout scm
  }
  stage('Clean'){
    sh('ant clean')
  }
}
