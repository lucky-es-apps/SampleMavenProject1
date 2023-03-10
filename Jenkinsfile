pipeline{
    agent any
    stages{
       stage('GetCode'){
            steps{
                git credentialsId: '798a09d4-0bb7-4426-976e-60d199c86321', url: 'https://github.com/lucky-es-apps/SampleMavenProject1.git'
            }
         }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('sonarqube-8.9.2') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar \
    }
        }
        }
       
    }
}
