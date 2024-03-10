pipeline {
  
    agent {
        label 'jenkins-worker'
    }
    
    tools{
        maven "Maven3"
    }

    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/Creativesarath420/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
        
        stage('Create Image'){
            steps{
               steps {
                	script {
                		sh 'ansible-playbook task.yml'
                	}
                }
            }
        }
    }
}
