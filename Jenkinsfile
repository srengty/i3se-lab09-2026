pipeline {
  agent any // can be run on any node/runner
  tools {
    maven 'Maven38'
  }
  stages {
    stage('Clone') { steps {
        git branch: 'main', url: 'https://github.com/srengty/i3se-lab09-2026.git'
    }}
    stage('Build')  { steps { 
        bat 'mvn clean package' } }
    stage('Test')   { steps { bat 'echo "test the project"' } }
    stage('Package'){ steps { bat 'echo "Package project"' } }
  }
  post {
    always  { junit '**/target/surefire-reports/*.xml' }
    success { echo '✔ Pipeline green' }
    failure { echo '✗ Build failed' }
  }
}