pipeline {
    agent any

    stages {
        stage('CloneRepo') {
            steps {
             echo 'Cloning Repo...'
             git url: 'https://github.com/prudhvireddy123/CovidDatabase.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Current Directory'
                bat 'dir'
                echo 'Building..'
                bat 'msbuild /p:Configuration=Release'
                echo "Build Completed and snapshot stored"
            }
        }
        stage('Backup Existing Database') {
            steps {
                echo 'Taking Backup....'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage("Cleanup Workspace") {
            steps {
             deleteDir()
            }
            
        }
    }
}

def cmd_exec(command) {
    return bat(returnStdout: true, script: "${command}").trim()
}