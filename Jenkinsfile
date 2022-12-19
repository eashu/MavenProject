pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
          }

    stages {
        stage('Build') {
                   steps {
                // Get some code from a GitHub repository
                git branch: 'master', credentialsId: '123456', url: 'https://github.com/eashu/MavenProject.git'

                // Run Maven on a Unix agent.
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
                
                //move war file 
                sh 'scp -o StrictHostKeyChecking=no /var/jenkins_home/workspace/MavenProject/webapp/target/webapp.war /var/jenkins_home/workspace/MavenProject/'               
                         }               
                      }
             }
     stages {
        stage('create image and container') {
                  steps {
                      dir('/var/jenkins_home/workspace/MavenProject/')   {
                          
                          
                      }
                      
                       }              
                  }
            }
}

