pipeline {
    agent any
    stages {
        stage('Welcome Step') {
            echo 'Start of pipeline'
        }
        stage('create samples files') {
            bat("cd > ./branch2_1/txtcd.txt")
            echo 'added cd text file'
            bat("data \t > txtdate.txt")
            echo 'added data text file'
        }
    }
}
        
