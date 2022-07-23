node {
    stage('git checkout') {
        //git 'https://github.com/DevOpsHubIN/deploy_nginx.git'
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/DevOpsHubIN/deploy_nginx.git']]])

    }
    stage('Build Dockr Image') {
        sh "docker build -t nginx:v${BUILD_NUMBER} ."
    }
}
