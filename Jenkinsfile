@Library('code') _

pipeline {
  agent {
    kubernetes {
      cloud 'dckubernetes'
      slaveConnectTimeout 300
      yamlFile "2x4.yaml"
    }
  }
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
  }
  stages {
    stage('prep-git-repo') {
      steps {
        sh '''
    set -eu
    env
    git config user.email "clearbanc@clearbanc.com" && git config user.name "clearbanc"
    git remote -v
    git branch -r
  '''
      }
    }
    stage('Hello') {
      steps {
        sh '''
          java -version
        '''
      }
    }
  }
}
