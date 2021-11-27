pipeline {
  agent {
    docker {
      image 'python:2-alpine'
    }

  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'sh \'python -m py_compile sources/add2vals.py sources/calc.py\' '
          }
        }

        stage('test') {
          steps {
            sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py'
          }
        }

      }
    }

  }
}