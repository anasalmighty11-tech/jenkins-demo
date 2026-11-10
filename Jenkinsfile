pipeline {
    agent any
    stages {
        stage("build") { steps { echo 'Building...' } }
        stage("test")  { steps { echo 'Testing...' } }
        stage("deploy") {
            when { branch 'main' }
            steps { echo 'Deploying...' }
        }
    }
}
