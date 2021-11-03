#!/usr/bin/env groovy

def printParams(def params){
  def cdlParams = '$params';
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
                    echo "Saving json file"
                    def rootDir = pwd()
                    File file = new File("$rootDir/zoc.json");
                    def data = [
                        bek: "Bogdan",
                        centar: "Pekovic"
                    ]
                    printParams(data);
                    def first = load "${rootDir}/first.groovy"
                    first.test1()
                }
            }
        }
        stage('Load json data') { 
            steps {
                echo "Load json data"
                script{
                    def rootDir = pwd()
                    def config = new groovy.json.JsonSlurper().parse(new File("$rootDir/zoc.json"))
                    printfln config
                }
            }
        }
        stage('Deploy') { 
            steps {
                echo "Deploy"
            }
        }
    }
}
