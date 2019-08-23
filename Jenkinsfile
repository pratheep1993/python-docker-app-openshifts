node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'Github-ID', url: 'https://github.com/pratheep1993/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "python_web/pratheep1993"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: ""]) {
          sh 'docker tag python_web/pratheep1993 python_web/pratheep1993:dev'
          sh 'docker push python_web/pratheep1993s:dev'
          sh 'docker push python_web/pratheep1993:latest'
      }
    }
   
   stage("App deployment started"){
     
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   
























}
