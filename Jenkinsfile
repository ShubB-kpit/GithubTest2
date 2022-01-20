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
        stage('Delete test.zip file') {
            if (fileExists('test.zip')) {
                new File('test.zip').delete()
            } else {
                println "test.zip file not found"
            }
        }
        stage('Archive') {
            steps {
                zip zipFile: 'test.zip', archive: false, dir: 'branch2_1'
                archiveArtifacts artifacts: 'test.zip', fingerprint: true
            }
        }
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
    }
}
        
