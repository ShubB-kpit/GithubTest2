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
                bat("date /t > ./branch2_1/txtdate.txt")
                echo 'added data text file'
                echo "path: ${JOB_URL}"
                
            }
        }
        stage('build myB') {
            steps {
                build(job: '../gitTest2_repo/myB',
                      parameters: [string(name: 'dataFromBuildPath', value: "${BUILD_URL}/execution/node/3/ws/branch2_1")],
                      wait: false, 
                      propagate: false
                     )
            }
        }
    }
}
        
