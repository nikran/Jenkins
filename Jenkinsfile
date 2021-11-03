#!/usr/bin/env groovy
pipeline {
    agent any 
    stages {
        stage('Checkout code') {
            steps {
                checkout scm
            }
        }
        stage('Build') { 
            steps {
                echo "Build" 
            }
        }
        stage('Test') { 
            steps {
                echo "Test"
            }
        }
        stage('Deploy') { 
            steps {
                echo "Deploy"
            }
        }
    }
}
