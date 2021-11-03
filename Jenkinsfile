#!/usr/bin/env groovy

def printParams(def params){
  def cdlParams = "'$params'";
  println cdlParams;  
    
}
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
                
                script{
                    echo "Exec Groovy"
                    def data = [
                        bek: "Bogdan",
                        centar: "Pekovic"
                    ];
                    printParams(groovy.json.JsonOutput.toJson(data));
                    def rootDir = pwd();
                    def first = load "${rootDir}/first.groovy"
                    first.test1()
                }
            }
        }
        stage('Build') { 
            steps {
                echo "Build"
            }
        }
        stage('Deploy') { 
            steps {
                echo "Deploy"
            }
        }
    }
}
