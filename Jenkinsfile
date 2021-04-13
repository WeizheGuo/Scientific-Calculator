pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''git clone https://github.com/WeizheGuo/Scientific-Calculator.git
cd Scientific-Calculator/Calculator
mvn clean install'''
      }
    }

  }
}