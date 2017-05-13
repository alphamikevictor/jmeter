#!groovy
node {
  stage('Get Repository'){
    checkout scm
  }
  stage('Clean'){
    sh('ant clean')
  }
  stage('Download Jars'){
    sh('ant download_jars')
  }
  stage('Build'){
    sh('ant')
  }
  stage('Report'){
    echo currentBuild.durationString
  }
}
