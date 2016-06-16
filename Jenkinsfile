#!groovy

stage 'Dev Build'
node {
    try{
         checkout([$class: 'GitSCM',
         branches: [[name: '*/newBranch']])
         //doGenerateSubmoduleConfigurations: false,
         //extensions: [[$class: 'RelativeTargetDirectory', 
         //relativeTargetDir: 'subdirectory1']], submoduleCfg: []) 
         //userRemoteConfigs: [[url: 'repo1.git']]])
       //sh 'git merge master'
      // sh 'git push origin newBranch'
        //push -u origin newBranch 
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
