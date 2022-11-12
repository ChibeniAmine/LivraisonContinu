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
                          sh " cd /Myapp/node_modules "
                          sh " ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "
                            }
                     }
                            }


                }
}














