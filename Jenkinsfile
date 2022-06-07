node('MASTER') {
    stage('SCM') {
        git 'https://github.com/DurgaKd/spring-petclinic.git'
    }
    stage('build'){
        sh 'mvn package'
    }
    stage('postbuild'){
        junit '**/TEST-*.xml'
        archive '**/*.war'
    }
}