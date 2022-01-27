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
                bat 'dir /a:h /b /s'
                cleanWs()
                bat 'dir /a:h /b /s'
                
            }
        }
        stage('copy files from main branch') {
            steps {
                script {
                    //echo "param: ${params.dataFromBuildPath}"
                    //bat("copy ${params.dataFromBuildPath}/txt*.txt ./branch2_1")
                    //sh('''git clone https://github.com/ShubB-kpit/GithubTest.git
                    //git fetch origin
                    //git checkout "main" "origin/main"
                    //''')
                    script {
                       // The below will clone your repo and will be checked out to master branch by default.
                       git url: 'https://github.com/ShubB-kpit/GithubTest.git'
                       // Do a ls -lart to view all the files are cloned. It will be clonned. This is just for you to be sure about it.
                       //sh "ls -lart ./*" 
                       // List all branches in your repo. 
                       //sh "git branch -a"
                       // Checkout to a specific branch in your repo.
                       //sh "git checkout main"
                       bat 'dir /a:h /b /s'
                    }
                }
            }
        }
    }
}
