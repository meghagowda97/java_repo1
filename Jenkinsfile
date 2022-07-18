pipeline {
agent {
  label 'slave-label1'
}
stages {
  stage('Git checkout') {
    steps {
     git 'https://github.com/meghagowda97/java_repo1.git'
    }
  }
  stage('Build') {
  steps {
    sh 'mvn clean install' }
}
  stage('Push to artifactory') {
  parallel {
  stage('Push to artifactory 1') {
  steps {
  sleep 15 }
  } 
  stage('Push to artifactory 2') {
  steps {
  sleep 15 }
  }
  }
  }
  
    stage('Deploy') {
    steps {
      sh 'sudo cp  /home/ec2-user/jenkin-1/workspace/parallel/target/*.war /opt/apache-tomcat-9.0.64/webapps/'
    }
  }

}
    
}
