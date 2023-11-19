node {
     stage('Clone repository') {
         checkout scm
     }

     stage('Build image') {
         app = docker.build("730135569722.dkr.ecr.ap-northeast-2.amazonaws.com/fiscicdlab")
     }

     stage('Push image') {
         docker.withRegistry('https://730135569722.dkr.ecr.ap-northeast-2.amazonaws.com', 'ecr:ap-northeast-2:ecr-fis-cicd') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
     }
  }
}
