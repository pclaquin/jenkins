pipeline {
  agent any
  options([parameters([booleanParam(defaultValue: false, description: 'this is bool', name: 'boolParam'), choice(choices: 'a\nb\nc', description: 'this is choice ', name: 'choiceThing'), text(defaultValue: 'defaultval', description: 'this is multiline', name: 'multiLIne'), password(defaultValue: 'nada', description: 'This is password', name: 'pass'), string(defaultValue: 'defaultparam', description: 'This is string param', name: 'stringParam')]), pipelineTriggers([])])
  stages {
    stage('Input') {
      steps {
        sh 'bash setup.sh'
      }
    }
    stage('Configuration initiale') {
      steps {
        sh 'bash setup.sh'
      }
    }
  }
}
