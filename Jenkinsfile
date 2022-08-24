
node(){
stage("git chekcout"){
 checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'gitkey', url: 'https://github.com/muraliphani/RentalCarsV2.git']]])
}

stage("Sonar Analysis"){
       scannerHome = tool 'sonarqubescanner'
       withSonarQubeEnv('sonarqube') {
            sh "${scannerHome}/bin/sonar-scanner"
           // sh "mvn clean deploy sonar:sonar"
        }
       timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
        }

   }

stage("Maven build"){

    sh "mvn package"
}



}