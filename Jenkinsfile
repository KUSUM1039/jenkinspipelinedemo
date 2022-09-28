pipeline {
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    // agent section is mandatory
    agent any
    
    stages{
        
        stage('Clone the repo')
        {
            steps{
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }
        
        stage('Compile the code')
        {
            steps{
                sh 'mvn compile'
            }
        }
        
        stage('Code Review')
        {
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        
        stage('Unit Testing')
        {
            steps{
                sh 'mvn test'
            }
            post{
                success{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Package')
        {
            steps{
                sh 'mvn package'
            }
        
        }
        
        stage('Deploy')
        {
            steps{
                echo 'Deploy Code'
            }
        
        }
        
    }
      
}
