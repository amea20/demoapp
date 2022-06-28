pipeline {
    agent {
        node {
            label 'Windows-Worker-1'
        }
    }
     triggers {
         pollSCM('* * * * 1-5')
     }
    options {
        timeout(time: 1, unit: 'HOURS')
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    stages {
        stage('Build') {
            steps {
              bat "dir"
              powershell "New-Item -ItemType File Test.txt"
              powershell "'Hello world' | Out-File -FilePath ./Test.txt"
              powershell "Get-Content Test.txt"
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
