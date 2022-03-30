node {
checkout(scm)
    withCredentials(bindings: [usernamePassword(credentialsId: 'Win_ID', passwordVariable: 'WIN_PASS', usernameVariable: 'WIN_USER')]) {
    stage ('Run the Job'){
        sh '''
        ansible-playbook site.yml -i hosts.ini
        '''
    }
    }
} 
