node{
    stage('git checkout'){
        echo 'git checkout'
        git 'https://github.com/ashinv121/addresbook-20.git'
        
    }
    stage('build'){
        
        sh 'mvn clean package'
    }
    stage('tomcat deploy'){
        
        deploy adapters: [tomcat9(credentialsId: 'tomcat9', path: '', url: 'http://172.31.45.182:8080')], contextPath: 'address-book2.0', war: '**/*.war'
    }
    
}
