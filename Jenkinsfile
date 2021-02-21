pipeline {
    agent any
    environment {
        PATH = "/opt/maven/apache-maven-3.6.3/bin:$PATH"
    }

    stages {
        stage('git') {
            steps {
                git 'https://github.com/rajakarish/hello-world1.git'
            }
        }
        stage('maven') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat8(credentialsId: 'Tomcat_credentials', path: '', url: 'http://18.218.61.39:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}

