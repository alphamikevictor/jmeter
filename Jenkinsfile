#!groovy
def antTool
node {
  stage('Config Ant Tool'){
    antTool = tool name:'ANT'
  }
  stage('Get Repository'){
    checkout scm
  }
  stage('Clean'){
    bat("${antTool} clean")
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
