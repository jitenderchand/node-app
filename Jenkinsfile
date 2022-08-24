pipeline {
    agent any
    
    environment {
     imageName = "jchand3/backend-test"
     dockerhub = credentials('dockerhub')
     secret = credentials('docker')
    }

    stages {
        
        // stage('Git checkout') {
        //     steps {
        //         git branch: 'main', url: 'https://github.com/jitenderchand1/node-app.git'
        //     }
        // }
        //  stage('Code Scanning') {
        //     environment {
        //         scannerHome = tool  'sonar-scanner';
        //     } 
        //     steps {
        //             sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=nodejs_app -Dsonar.sources=. -Dsonar.host.url=http://host.docker.internal:9000 -Dsonar.login=sqp_c2946bb814783db7b3c40233ffbc5b54f952106e"
        //     }
        // }
        
        // stage('Build') {
        //     steps {
        //         nodejs('nodejs') {
        //             sh "npm install"        
        //         }
                
        //     }
        // }
        
        // stage('Dependency scanning') {
        //     steps {
        //         nodejs('nodejs') {
        //             sh "npm audit --fix || true"
        //             sh "npm install -g npm-audit-html"
        //             sh "npm audit --json | npm-audit-html"
                    
        //              publishHTML (target: [
        //               allowMissing: false,
        //               alwaysLinkToLastBuild: false,
        //               keepAll: true,
        //               reportDir: '.',
        //               reportFiles: 'npm-audit.html',
        //               reportName: "Npm audit report"
        //             ])
        //         }
                
        //     }
        // }
        
        // stage('Docker build & publish') {
        //     steps {
        //         sh '''
        //             docker build -t $imageName:$BUILD_NUMBER .
        //             echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin
        //             export DOCKER_CONTENT_TRUST_REPOSITORY_PASSPHRASE=$secret
        //             docker -D trust sign $imageName:$BUILD_NUMBER
        //         '''
        //         // script {
        //         //      docker.withRegistry('', 'dockerhub') {
        //         //         withCredentials([string(credentialsId: 'docker', variable: 'SECRET')]) {
        //         //             sh "echo ********"
			     //        //   echo "ls -a ${WORKSPACE}@tmp"
			     //        //   sh "echo $HOME"
			     //        //   sh "ls -la $HOME"
        //         //             sh "echo $NODE_NAME"
        //         //             sh '''
        //         //             docker ps -a
        //         //             export DOCKER_CONTENT_TRUST_REPOSITORY_PASSPHRASE=password
        //         //             docker -D trust sign $imageName:$BUILD_NUMBER
        //         //             '''
        //         //         }    
        //         //     }
        //         // }
                
        //     }
        // }
        stage('Scan Image') { 
            agent {
                docker { 
                    image 'node:16.13.1-alpine'
                }
            }
            steps {
                 sh 'node --version'
            }
        }
    }
}
