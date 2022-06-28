pipeline {
    agent {
        node {
            label 'Windows-Worker-1'
        }
    }
//     triggers {ss
//         pollSCM('* * * * 1-5')
//     }
    options {
        timeout(time: 1, unit: 'HOURS')
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    stages {
        stage('Build') {
            steps {
              bat "dir"
              powershell "New-Item -ItemType File Test.txt"
              bat "dir"
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
