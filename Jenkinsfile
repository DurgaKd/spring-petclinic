node('MASTER') {
    stage('scm') {
        git branch: 'main', url: 'https://github.com/DurgaKd/spring-petclinic.git'
    }
    stage('build'){
        sh 'mvn package'
    }
    stage('postbuild'){
        junit '**/TEST-*.xml'
        archive '**/*.war'
    }
}