pipeline {
  agent any // can be run on any node/runner
  stages {
    stage('Clone') { steps {
        git url: 'https://github.com/srengty/i3se-lab09-2026.git'
    }}
    stage('Build')  { steps { 
        bat 'echo "build the project"' } }
    stage('Test')   { steps { bat 'echo "test the project"' } }
    stage('Package'){ steps { bat 'echo "Package project"' } }
  }
  post {
    always  { echo '**/target/surefire-reports/*.xml' }
    success { echo '✔ Pipeline green' }
    failure { echo '✗ Build failed' }
  }
}