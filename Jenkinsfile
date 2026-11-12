def gv
pipeline {
    agent any
    parameters {
        choice(name: 'Version', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Version to build')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Execute tests')
    }
    stages {
        stage("init") { 
            steps { 
                script {
                    gv = load 'script.groovy'
                }  
            } 
        }
        stage("build") { 
            steps { 
                script {
                    gv.buildAPP()
                }
                
            } 
        }
        stage("test")  { 
            when { expression { params.executeTests } }
            steps { 
                script {
                    gv.testAPP()
                }
            }
        }
        stage("deploy") {
            steps { 
                script {
                    gv.deployAPP()
                }
                
            } 
        }
    }
    }

