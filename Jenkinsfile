#!/usr/bin/env groovy

def printParams(def params){
  def cdlParams = params;
  println "bek je $params.bek";
  if (!cdlParams["plej"]){
      println "plej ne postoji"
  }
    
  println groovy.json.JsonOutput.toJson(data);  
    
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
                    data["krilni_centar"] = "novica";
                    printParams(data);
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
