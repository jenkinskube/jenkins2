pipeline {

  environment {
    registry = "jfcoronado/myweb"
    dockerImage = ""
  }

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/jenkinskube/jenkins2.git'
      }
    }


    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "myweb.yaml", kubeconfigId: "kubeconfig" )
        }
      }
    }
  }
}
