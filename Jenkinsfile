#!groovy

stage 'Dev Build'
node {
    try{
        checkout scm
        mvn 'clean compile'
    }catch(Exception e){
        echo "in exception"
    }
}

stage 'Unit Testing'
node {
    try{
         mvn 'test'
    }catch(Exception e){
        echo "In exception"
    }
   
}

input message: "Ready for Dev Deployment?"

stage name: 'Dev Deployment', concurrency: 1
node {
    sh 'ansible-playbook -i playbook1.yml'
}

def mvn(args) {
    sh "${tool 'Maven'}/bin/mvn ${args}"
}
