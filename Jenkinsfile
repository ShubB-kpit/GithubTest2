pipeline {
    parameters {
        string(name: 'dataFromBuildPath',
                defaultValue: 'job/gitTest2_repo/job/main/11/execution/node/3/ws/branch2_1',
                description: 'Please give the workspace path of main')
    }
    agent any
    stages {
        stage('Welcome Step') {
            steps { 
                echo 'Welcome to the LambdaTest'
            }
        }
        stage('check if py file exists'){
            steps {
                script {
                    if(fileExists("./branch2_1/pyTest1.py")) {
                        echo 'py file exists'
                    }
                    else {
                        echo '404: file not exists'
                    }
                    echo "JOB_NAME: ${JOB_NAME}"
                    echo "WORKSPACE: ${WORKSPACE}"
                }   
            }
        }
        stage('copy files from main branch') {
            steps {
                script {
                    echo "param: ${params.dataFromBuildPath}"
                    //bat("copy ${params.dataFromBuildPath}/txt*.txt ./branch2_1")
                }
            }
        }
    }
}
