pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/fw190d9/GitOps.git will replace by sed command before RUN
	// TEST03
        git url: 'https://github.com/fw190d9/GitOps.git', branch: 'main'
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
