pipeline {
    parameters {
        string(name: 'artName',
                defaultValue: '',
                description: 'name of archive')
        string(name: 'prjName',
                defaultValue: '',
                description: 'name of project')
        string(name: 'buildNo',
                defaultValue: '',
                description: 'number of build')
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
        stage('pull artifact') {
            steps {
                /*
                copyArtifacts filter: "${param.artName}", fingerprintArtifacts: true, projectName: "${param.prjName}", selector: specific("${param.buildNo}")
                unzip zipFile: "${param.artName}", dir: './archive_new'
                bat 'dir archive_new'
                */
                sh 'ls'
                clearWs()
                sh 'ls'
            }
        }
        /*
        stage('copy files from main branch') {
            steps {
                script {
                    echo "param: ${params.dataFromBuildPath}"
                    //bat("copy ${params.dataFromBuildPath}/txt*.txt ./branch2_1")
                }
            }
        }
        */
    }
}
