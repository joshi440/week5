pipeline {

    agent any

    stages {


        stage('Compiler') {
            steps {
                bat 'javac Factorial.java TestFactorial.java'
            }
        }

        stage('Test') {
            steps {
                bat 'java TestFactorial'
            }
        }

        stage('Run') {
            steps {
                bat 'java Factorial'
            }
        }

        stage('Package JAR') {
            steps {
                echo 'Build'
                bat 'jar cfm Factorial.jar manifest.txt Factorial.class'
            }
        }

        stage('Archive JAR') {
            steps {
                echo 'Deploy'
                archiveArtifacts artifacts: 'Factorial.jar'
            }
        }
    }
}
