#!groovy

stage 'Dev Build'
node {
    try{
        git checkout scm
        git merge newBranch
        git push -u origin newBranch 
        //mvn 'clean compile'
    }catch(Exception e){
        throw e
    }
}

/*stage 'Unit Testing'
node {
    try{
         mvn 'test'
    }catch(Exception e){
        echo "In exception"
    }
   
}
*/
/*input message: "Ready for Dev Deployment?"

stage name: 'Dev Deployment', concurrency: 1
node {
    println env.JOB_NAME
  // ansiblePlaybook credentialsId: '9e6a8036-c691-468b-ad4c-43a84ed08256', extras: 'warfile=/home/azureuser/CounterWebApp', installation: 'Ansible', inventory: '/etc/ansible/hosts', playbook: '/home/azureuser/playbook.yml', sudoUser: null
}
*/
def mvn(args) {
    sh "${tool 'Maven'}/bin/mvn ${args}"
}
