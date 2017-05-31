pipeline {
  agent any
  stages {
    stage('Configuration initiale') {
      steps {
        sh '"bash setup.sh $IDENTIFIANT $PASSWORD"'
        sh '"bash $PIPELINE_HOME/windows/inventory.sh $MACHINE $SNAPSHOT $IDENTIFIANT $PASSWORD $SERVEUR"'
        ansiblePlaybook(playbook: '"$PIPELINE_HOME/windows/playbookCreateInstallDir.yml"', inventory: '"$PIPELINE_HOME/windows/inventory.txt"')
        input 'Test'
      }
    }
  }
}