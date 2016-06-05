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

stage 'Static Code Analysis - Sonar'
node {
    try{
        mvn 'sonar:sonar -Dsonar.host.url=http://cloudbagmtweb.southeastasia.cloudapp.azure.com/sonar/'
    }catch(Exception e){
        echo "in Exception"
    }
   
}

input message: "Ready for Dev Deployment?"

stage name: 'Dev Deployment', concurrency: 1
node {
   echo 'deploying..'
}

def mvn(args) {
    sh "${tool 'Maven'}/bin/mvn ${args}"
}
