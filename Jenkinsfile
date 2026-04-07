pipeline { 
  agent any
  tools { 
    maven 'Maven'
  }
  stages {
    stage ('Checkout') {
      steps {
        git branch: 'master', url:'https://github.com/rakshitha-v1/my-maven-app.git'
      }
    }
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Test') {
      steps {
        sh 'mvn test'
      }
    }
    stage('Run Application') {
      steps {
        sh 'java -jar target/my-maven-app-1.0-SNAPSHOT.jar'
      }
    }
  }
  post {
    success {
      echo 'Build and Deployment successful!'
    }
    failure {
      echo 'Build failed!'
    }
  }
}
