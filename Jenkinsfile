node{

    stage('SCM Checkout')
    {
        git 'https://github.com/sree224/DevOps-project.git'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'docker-compose build'
        sh 'docker-compose up -d'
    }
    stage('PUSH image to Docker Hub')
    {
        withCredentials([string(credentialsId: 'docker', variable: 'DHPWD')]) 
        {
            sh "docker login -u cvenkat224 -p ${DHPWD}"
        }
        sh 'docker push cvenkat224/phpmysql_app'
    }
}
