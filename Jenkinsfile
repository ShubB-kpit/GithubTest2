pipeline {
    agent any
    stages {
        stage('Welcome Step') {
            steps {
                echo 'Start of pipeline'
            }
        }
        stage('create samples files') {
            steps {
                bat("cd > ./branch2_1/txtcd.txt")
                echo 'added cd text file'
                bat("date /t > txtdate.txt")
                echo 'added data text file'
                echo "path: ${RUN_DISPLAY_URL}"
            }
        }
    }
}
        
