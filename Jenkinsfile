pipeline {
    agent any

    stages {
        stage('SCM stage') {
            steps {
                echo 'Hello World batch3 champs'
                git 'https://github.com/wakaleo/game-of-life.git'
            }
        }    
        
        stage('artifact build stage') {
            steps {
                echo 'building with maven tool'
                sh 'mvn clean install'
            }
       }
    
        stage('deploy to tomcat stage') {
            steps {
                echo 'building with maven tool'
                deploy adapters: [tomcat9(credentialsId: '980da2ee-ced9-4358-a001-169fbac22537', path: '', url: 'http://54.167.99.89:8080/')], contextPath: null, war: '"**/*.war"'   

            }
        }
    }
}
