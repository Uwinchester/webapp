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
