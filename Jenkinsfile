pipeline {
 agent any
 tools{
  maven 'Maven' 
 }
 stages {
  stage ('initialze') {
   steps {
    sh 'echo "PATH = ${PATH}"'
    sh 'echo "M2_HOME = ${M2_HOME}"'
   }
  }
  stage ('secrets') {
   steps {
    sh 'docker run gesellix/trufflehog --json https://github.com/Uwinchester/webapp.git > trufflehog.json'
    sh 'cat trufflehog.json'
   }
  }
  stage ('build') {
   steps {
    sh 'mvn clean package'
   }
  }
  stage ('Deploy') {
   steps{
    sh 'mv target/*.war /home/usef/Downloads/apache-tomcat-10.1.39/webapps/webapp.war'
   }
  } 
 }
}
