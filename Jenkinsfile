node {
  stage 'Checkout'{
  git 'https://github.com/Nitin-2015/docker-pipeline-demo.git'
    sh label: '', script: 'ls'
    sh label: '', script: './sonar.sh'
  }
 
  stage 'Docker build'
  docker.build('jenkins_ecr')
 
  stage 'Docker push'
  docker.withRegistry('https://561337794842.dkr.ecr.us-east-2.amazonaws.com/jenkins_ecr:latest', 'ecr:us-east-2:d2f221f3-4515-46cc-800b-b089de98dbf3') {
    docker.image('jenkins_ecr').push('latest')
  }
}
