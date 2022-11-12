pipeline
{
    agent any
        stages {
           stage ('Pull') {
               steps {
                  script{
                     checkout([$class: 'GITSCM', branches: [[name: '*/master']],
                      userRemoteConfigs: [[
                         url: 'https://github.com/ChibeniAmine/LivraisonContinu.git']]])
                        }
                      }
                          }
                }
}














