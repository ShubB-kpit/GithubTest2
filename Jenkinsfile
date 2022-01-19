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
                echo "path: ${JOB_URL}"
            }
        }
        stage('build myB') {
            steps {
                build '../gitTest2_repo/myB'
            }
        }
    }
}
        
