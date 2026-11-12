pipeline {
    agent any
    parameters {
        choice(name: 'Version', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Version to build')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Execute tests')
    }
    stages {
        stage("build") { 
            steps { 
                echo 'Building...' 
            } 
        }
        stage("test")  { 
            when { expression { params.executeTests } }
            steps { echo 'Testing...'
            }
        }
        stage("deploy") {
            steps { 
                echo 'Deploying...' 
                echo "Deploying version ${params.Version}"
            } 
        }
    }
    }

