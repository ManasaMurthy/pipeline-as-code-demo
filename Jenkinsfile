#!groovy

/*stage 'Dev Build'
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
   
}*/

input message: "Ready for Dev Deployment?"

stage name: 'Dev Deployment', concurrency: 1
node {
    println {properties.displayName.get(0).displayName}
   //ansiblePlaybook credentialsId: '9e6a8036-c691-468b-ad4c-43a84ed08256', extras: 'warfile=/home/azureuser/CounterWebApp.war', installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/azureuser/playbook.yml', sudoUser: null
}

def mvn(args) {
    sh "${tool 'Maven'}/bin/mvn ${args}"
}
