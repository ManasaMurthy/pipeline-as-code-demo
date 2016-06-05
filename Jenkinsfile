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
    println env.JOB_NAME
   ansiblePlaybook credentialsId: '3709ca68-6dcc-466b-9b88-fce49c46fa33',extras: 'warfile=/home/azureuser/CounterWebApp.war', installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/azureuser/playbook.yml', sudoUser: null
}

def mvn(args) {
    sh "${tool 'Maven'}/bin/mvn ${args}"
}
