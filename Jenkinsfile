#!groovy
node {
  stage('Get Repository'){
    checkout scm
  }
  stage('Clean'){
    bat('ant clean')
  }
  stage('Download Jars'){
    bat('ant download_jars')
  }
  stage('Build'){
    bat('ant')
  }
  stage('Report'){
    echo currentBuild.durationString
  }
}
