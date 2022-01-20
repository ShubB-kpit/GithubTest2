library identifier: 'mylibraryname@main',
    // 'mylibraryname' is just an identifier, it can be anything you like
    // 'master' refers to a valid git ref (branch)
    retriever: modernSCM([
      $class: 'GitSCMSource',
      remote: 'https://github.com/ShubB-kpit/myJenkinSharedLib.git'
])


//@Library('myJenkinSharedLib')_

//import static org.utils.PipelineUtils.*

pipeline {
    agent any
    stages {
        stage('Welcome Step') {
            steps {
                echo 'Start of pipeline'
            }
        }
        stage('Demo library') {
            steps {
                echo 'Hello world'
                sayHello 'shubham'
            }
        }
        stage('create samples files') {
            steps {
                //bat("cd > ./branch2_1/txtcd.txt")
                sh("ls > ./branch2_1/txtcd.txt")
                echo 'added cd text file'
                //bat("date /t > ./branch2_1/txtdate.txt")
                sh("date > ./branch2_1/txtdate.txt")
                echo 'added data text file'
                echo "path: ${JOB_URL}"
                
            }
        }
        stage('check if zip file exists'){
            steps {
                script {
                    if(fileExists('./test.zip')) {
                        echo 'zip file exists'
                        deleteFile('test.zip')
                    }
                }
            }
        }
        /*
        stage('Archive') {
            steps {
                zip zipFile: 'test.zip', archive: false, dir: 'branch2_1'
                archiveArtifacts artifacts: 'test.zip', fingerprint: true
            }
        }
        /*
        stage('build myB') {
            steps {
                build(job: '../gitTest2_repo/myB',
                      parameters: [string(name: 'artName', value: 'test.zip'),
                                  string(name: 'prjName', value: "${JOB_NAME}"),
                                  string(name: 'buildNo', value: "${BUILD_NUMBER}")],
                      wait: false, 
                      propagate: false
                     )
            }
        }
        */
    }
}
        
