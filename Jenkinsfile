pipeline {
   agent any
   stages{
       stage('git clone'){
           steps{
                git credentialsId: '798a09d4-0bb7-4426-976e-60d199c86321', url: 'https://github.com/lucky-es-apps/SampleMavenProject1.git'  
           }        
       }
       stage('build the code'){
           steps{
              sh 'mvn package'
           }
       }
       stage('archive the artifacts'){
           steps{
              archive 'target/*.jar'
           }          
       }
       stage('publish the junit reports'){
           steps{
              junit 'target/surefire-reports/*.xml'
           }
           
       }

   }
}
