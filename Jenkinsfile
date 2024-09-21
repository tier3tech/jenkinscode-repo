pipeline{
    
    agent any
    tools{
        maven 'mymaven'
        
        
    }
    stages{
        stage('clone repo'){
            
            steps{
                
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }
        stage('build and deploy'){
            steps{
                sh 'mvn package'
            }
            post{
                success{
                    deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://localhost:9090/')], contextPath: null, war: '**/*.war'
                }
            }
        }   
    }
    
}
