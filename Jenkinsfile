#!groovy
node {
  stage('Get Repository'){
    checkout scm
  }
  stage('Clean'){
    sh('ant clean')
  }
  stage('Build'){
    sh('ant')
  }
  stage('Report'){
    echo currentBuild.durationString
  }
}
