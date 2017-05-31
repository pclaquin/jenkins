pipeline {
agent any
    
stages {

    stage('Configuration initiale') {
        steps {
        sh "bash $PIPELINE_HOME/windows/setup.sh $IDENTIFIANT $PASSWORD"
        sh "bash $PIPELINE_HOME/windows/inventory.sh $MACHINE $SNAPSHOT $IDENTIFIANT $PASSWORD $SERVEUR"
        ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookCreateInstallDir.yml",
                        inventory: "$PIPELINE_HOME/windows/inventory.txt")
        switch (LANGAGE) {
            case "PowerShell":
                ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookCopyFiles.yml",
                                inventory: "$PIPELINE_HOME/windows/inventory.txt")
        }
        }
    }
}
  /*          break
            case "Batch":
                ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookCopyFilesBat.yml",
                                inventory: "$PIPELINE_HOME/windows/inventory.txt")
            break
        }
        }
    }

    stage('Snapshot1') {
        steps {
        ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookTakeSnapshotClean.yml",
                        inventory: "$PIPELINE_HOME/windows/inventory.txt")
    }
    }
    stage('Installation') {
        steps {
        switch (LANGAGE) {
            case "PowerShell":
                ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookInstall.yml",
                                inventory: "$PIPELINE_HOME/windows/inventory.txt")
            break
            case "Batch":
                ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookInstallBat.yml",
                                inventory: "$PIPELINE_HOME/windows/inventory.txt")
            break
        }
        }
    }
    stage('Vérification Installation') {
        steps {
        if(VERIFICATION_MANUELLE=='Oui'){
        input 'En attente de la vérification manuelle'
        }
        else {
            ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookVerifInstall.yml",
                        inventory: "$PIPELINE_HOME/windows/inventory.txt")

        }
        }
    }
    stage('Désinstallation') {
        steps {
        switch (LANGAGE) {
            case "PowerShell":
                ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookUninstall.yml",
                                inventory: "$PIPELINE_HOME/windows/inventory.txt")
            break
            case "Batch":
                ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookUninstallBat.yml",
                                inventory: "$PIPELINE_HOME/windows/inventory.txt")
            break
        }
        }
    }
    stage('Vérification Désinstallation') {
        steps {
        if(VERIFICATION_MANUELLE=='Oui'){
        input 'En attente de la vérification manuelle'
        }
        else {
            ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookVerifUninstall.yml",
                        inventory: "$PIPELINE_HOME/windows/inventory.txt")

        }
        }
    }
    stage('Retour au Snapshot') {
        steps {
        ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookRevertSnapshot.yml",
                        inventory: "$PIPELINE_HOME/windows/inventory.txt")
    }
    }
     stage('Install') {
         steps {
         switch (LANGAGE) {
            case "PowerShell":
                ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookInstall.yml",
                                inventory: "$PIPELINE_HOME/windows/inventory.txt")
            break
            case "Batch":
                ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookInstallBat.yml",
                                inventory: "$PIPELINE_HOME/windows/inventory.txt")
            break
        }
        }
    }
     stage('Vérification Installation') {
         steps {
        if(VERIFICATION_MANUELLE=='Oui'){
        input 'En attente de la vérification manuelle'
        }
        else {
            ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookVerifInstall.yml",
                        inventory: "$PIPELINE_HOME/windows/inventory.txt")


        }
        }
    }
    stage('Consolidation des snapshots') {
        steps {
        ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookDeleteSnapshots.yml",
                        inventory: "$PIPELINE_HOME/windows/inventory.txt")
    }
    }
    stage('Ultime Snapshot') {
        steps {
        ansiblePlaybook(playbook: "$PIPELINE_HOME/windows/playbookTakeSnapshot.yml",
                        inventory: "$PIPELINE_HOME/windows/inventory.txt")
    }
    }
}
}
*/
