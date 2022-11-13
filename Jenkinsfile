pipeline
{
    agent any
        stages {
           stage ('Pull') {
               steps {
                  
                     echo 'Pulling from Git' ;
                     git branch: 'master',
                     url : 'https://github.com/ChibeniAmine/LivraisonContinu.git' ;
                        

                      }
                          }

             
            stage ('Build') {
               steps {
                     script {
                          sh "npm -v "
                          sh "npm install --legacy-peer-deps"
                          sh " ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "
                            }
                     }
                            }
          
          
          
          stage('DockerImage'){
    steps {

          script{
          sh "ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml"
}


}
}

stage('Push to Dockerhub'){
    steps {

          script{
          sh "ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/host.yml"
}


}
}
          
          stage('Monitoring') {
      steps {
        script {
           sh 'ansible-playbook Ansible/docker-compose.yml -i Ansible/inventory/hosts.yml'
          }
       }
    }


          


                }
}














