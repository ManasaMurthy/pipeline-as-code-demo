#!groovy

stage 'gitmerge'
@NonCPS
node (){
  git checkout master 
  git merge newBranch
 git push -u origin master  
}

/*jettyUrl = 'http://localhost:8081/'

stage 'Dev'
node ('docker-cloud'){
    checkout scm
    mvn 'clean package'
    dir('target') {stash name: 'war', includes: 'x.war'}
}

stage 'QA'
parallel(longerTests: {
    runTests(30)
}, quickerTests: {
    runTests(20)
})

stage name: 'Staging', concurrency: 1
node ('docker-cloud') {
    deploy 'staging'
}

input message: "Does ${jettyUrl}staging/ look good?"
try {
    checkpoint('Before production')
} catch (NoSuchMethodError _) {
    echo 'Checkpoint feature available in CloudBees Jenkins Enterprise.'
}

stage name: 'Production', concurrency: 1
node ('docker-cloud') {
    sh "wget -O - -S ${jettyUrl}staging/"
    echo 'Production server looks to be alive'
    deploy 'production'
    echo "Deployed to ${jettyUrl}production/"
}

def mvn(args) {
    sh "${tool 'Maven 3.x'}/bin/mvn ${args}"
}

def runTests(duration) {
    node ('docker-cloud')  {
        checkout scm
        runWithServer {url ->
            mvn "-o -f sometests test -Durl=${url} -Dduration=${duration}"
        }
    }
}

def deploy(id) {
    unstash 'war'
    sh "cp x.war /tmp/webapps/${id}.war"
}

def undeploy(id) {
    sh "rm /tmp/webapps/${id}.war"
}

def runWithServer(body) {
    def id = UUID.randomUUID().toString()
    deploy id
    try {
        body.call "${jettyUrl}${id}/"
    } finally {
        undeploy id
    }*/
    def mvn(args) {
    sh "${tool 'Maven 3.x'}/bin/mvn ${args}"
}
