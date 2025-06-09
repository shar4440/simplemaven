pipeline{
  agent any

  tools{
    maven 'Maven'
  }

  stages{
    stage('checkout'){
      steps{
        git branch: 'master', url: 'https://github.com/shar4440/simplemaven.git'
      }
    }

    stage('build'){
      steps{
        sh 'mvn clean package'
      }
    }

    stage('test'){
      steps{
        sh 'mvn test'
      }
    }

    stage('run'){
      steps{
        sh 'java -jar target/simplemaven-1.0-SNAPSHOT.jar'
      }
    }
  }

  post{
    success{
      echo 'completed successfully'
    }
    failure{
      echo 'get failed'
    }
  }
}
