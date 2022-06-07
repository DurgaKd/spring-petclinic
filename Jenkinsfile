pipeline {
    agent { label 'MASTER'}
    triggers {
        cron ('* * * * *')
        pollSCM ('* * * * *')
    }
    stages {
        stage('scm') {
            steps {
                git branch:'main' , url:'https://github.com/DurgaKd/spring-petclinic.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
    }
    postbuild {
        success {
            archive '**/*.war'
            junit '**/TEST-*.xml'
        }
    }
}