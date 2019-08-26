node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'Github-ID', url: 'https://github.com/itrainbatman/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "manee2k6/itrainbatman"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: ""]) {
          sh 'docker tag manee2k6/itrainbatman manee2k6/itrainbatman:dev'
          sh 'docker push manee2k6/itrainbatman:dev'
          sh 'docker push manee2k6/itrainbatman:latest'
      }
    }
    stage("App deployment started"){
     sh 'oc login --token=9fu1m1qExDwwZr03qvl-O9rkhOobCxFw7TKHlfHr99c --server=https://api.us-east-1.online-starter.openshift.com:6443
'
    // sh 'oc new-project creativetech'
      
     sh 'oc new-app pratheep1993/pythonimage:dev --name python'
     sh 'oc expose svc python --name=python'
     sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   


   
























}
