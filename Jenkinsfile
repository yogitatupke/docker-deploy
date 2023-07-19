pipeline {
  agent any
  stages {
    stage ('23Q1-deploy') {
      steps {
        sh "yum install docker -y"
        sh "systemctl start docker"
        sh "systemctl enable docker"
       
        sh "docker run -itdp 80:80 --name yoga httpd"
        sh "docker cp index.html yoga:/usr/local/apache2/htdocs"
        sh "docker exec yoga chmod -R 777 /usr/local/apache2/"
      }
    }
  }
}
