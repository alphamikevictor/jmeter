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
    if (isUnix()){
      sh("${antTool}/bin/ant clean")
    }
    else{
      bat("${antTool}\\bin\\ant clean")
    }
  }
  stage('Download Jars'){
    withEnv(['ANT_OPTS="-Dproxy.user=praesges01 -Dproxy.host=8888 -Dproxy.user=y"']){
      if (isUnix()){
        sh("${antTool}/bin/ant ${env.ANT_OPTS} setproxy download_jars")
      }
      else{
        bat("${antTool}\\bin\\ant ${env.ANT_OPTS} setproxy")
        bat("${antTool}\\bin\\ant ${env.ANT_OPTS} download_jars")
      }
    }
  }
  stage('Build'){
    bat('ant')
  }
  stage('Report'){
    echo currentBuild.durationString
  }
}
