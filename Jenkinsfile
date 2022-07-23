node {
    stage('git checkout') {
        //git 'https://github.com/DevOpsHubIN/deploy_nginx.git'
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/DevOpsHubIN/deploy_nginx.git']]])

    }
    stage('Build Dockr Image') {
        sh "docker build -t ngnix:v${BUILD_NUMBER} ."
        sh "docker run -d -p 800${BUILD_NUMBER}:80 -it ngnix:v${BUILD_NUMBER} /bin/bash"
    }
}
