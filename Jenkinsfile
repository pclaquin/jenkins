pipeline {
  agent any
   parameters {
    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
   // string(name: 'Username', defaultValue: 'pclaquin', description: 'Un petit nom d\'utilisateur?')
//    string(name: 'Password')
  }
  stages {
    stage('Input') {
      steps {
        sh '"bash setup.sh $USERNAME $PASSWORD"'
      }
    }
  }
 
}
