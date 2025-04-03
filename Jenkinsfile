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
 }
}
