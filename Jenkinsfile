pipeline{
    agent any
    tools{ 
        maven 'Maven3'

     }
    stages{
        stage("CHECKOUT"){
            steps{
                git 'https://github.com/vvce23ise0101-eng/slack-demo'
            }
        }  
        stage("BUILD"){
            steps{
                dir('demo'){
                    bat 'mvn clean install'

                }
            }

        }
        stage("TEST"){
            steps{
                dir('demo'){
                  bat 'nvm test'
                }
            }
        }
          }
}