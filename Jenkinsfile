pipeline {
    agent {
        node {
            label 'Windows-Worker-1'
        }
    }
//     triggers {
//         pollSCM('* * * * 1-5')
//     }
    options {
        timeout(time: 1, unit: 'HOURS')
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    stages {
        stage('Build') {
            steps {
              cmd "dir"
              powershell "New-Item -ItemType File Test.txt"
              cmd "dir"
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
