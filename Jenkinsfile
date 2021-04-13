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

    stage('test') {
      parallel {
        stage('test') {
          steps {
            sh '''cd Scientific-Calculator/Calculator
mvn -Dtest=CalculatorSpec test'''
          }
        }

        stage('static analysis') {
          steps {
            sh '''cd Scientific-Calculator/Calculator
mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dlicense.skip=true -Dsonar.login="cbbbc45841aa6b486be88b8d1977346006a03b0d"'''
          }
        }

      }
    }

  }
}