#!/usr/bin/env groovy
pipeline {
    agent any 
    stages {
        stage('Checkout code') {
            steps {
                checkout scm
            }
        }
        stage('Executing Groovy') { 
            steps {
                
                def rootDir = pwd()
                def exampleModule = load "${rootDir}@script/Example.Groovy "
                exampleModule.exampleMethod()
                exampleModule.otherExampleMethod()
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
