pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/javython999/GitOps will replace by sed command before RUN
        git url: 'https://github.com/javython999/GitOps', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}