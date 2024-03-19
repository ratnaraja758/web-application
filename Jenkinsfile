pipeline
{
    agent any
    tools{
        maven "maven"
    }
      stages{
        stage('pulling code'){
            steps{
                git branch: 'main' , url: 'https://github.com/ratnaraja758/web-application.git'
            }
        }
         
         stage('Package'){
            steps{
                sh 'mvn package'
           }
        }
        
        stage('Deploy App in Appserver'){
             steps{
                echo "Deploy App in AppServer"
               deploy adapters: [tomcat9(credentialsId: 'Tomcat', path: '', url: 'http://16.16.139.191:8080/')], contextPath: null, war: '**/*.war'
            }
        }
          
    }
}
