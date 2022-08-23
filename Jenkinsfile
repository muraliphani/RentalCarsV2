
node(){
stage("git chekcout"){
 checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'gitkey', url: 'https://github.com/muraliphani/RentalCarsV2.git']]])
}
stage("Maven build"){

    sh "mvn package"
}
stage("Sonar Analysic"){

}

}