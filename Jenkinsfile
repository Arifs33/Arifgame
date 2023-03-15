pipeline {
  agent {
        label {
		
		    label "built-in"
			customWorkspace "/mnt/vol5"
		}
  }
  stages {
    stage('Deploy to Container-2') {
	    steps {
	       
	       sh "sudo docker volume create my-volume-5"
	       sh "sudo cp /mnt/vol5/index.html /var/lib/docker/volumes/my-volume-5/_data"
	       sh "chmod -R 777 /mnt/vol5/index.html"
	       sh "chmod -R 777 /var/lib/docker/volumes/my-volume-5/_data"
	       sh "sudo docker run -itdp 8081:80 -v my-volume-5:/usr/local/apache2/htdocs --name container-5 httpd"
	      
      }
    }
  }
}
