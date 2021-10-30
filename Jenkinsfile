pipeline {
  kubernetes {
      cloud 'dckubernetes'
      slaveConnectTimeout 300
      yamlFile "2x4.yaml"
    }
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
  }
  stages {
    stage('Hello') {
      steps {
        sh '''
          java -version
        '''
      }
    }
  }
}
