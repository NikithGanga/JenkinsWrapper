pipeline {
    agent any
    
    environment {
        JAVA_HOME = tool 'JDK11'
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Compile') {
            steps {
                sh '''
                javac HelloWorld.java
                javac SimpleTest.java
                '''
            }
        }
        stage('Test') {
            steps {
                sh 'java SimpleTest'
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            sh 'rm *.class'
        }
    }
}

