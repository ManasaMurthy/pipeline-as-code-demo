#!groovy

stage 'Dev Build'
node {
  //pipeline = load 'pipeline.groovy'
    //sh 'git checkout -b testBranch6'
    //sh 'git push testBranch6'
    sh 'git checkout newBranch'
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
