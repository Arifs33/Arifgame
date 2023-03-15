pipeline {
  agent {
        label {
		
		    label "built-in"
			customWorkspace "/mnt/vol4"
		}
  }
  stages {
    stage('Deploy to Container-2') {
	    steps {
	       
	       sh "sudo docker volume create my-volume-4"
	       sh "sudo cp /mnt/vol4/index.html /var/lib/docker/volumes/my-volume-4/_data"
	       sh "chmod -R 777 /mnt/vol4/index.html"
	       sh "chmod -R 777 /var/lib/docker/volumes/my-volume-4/_data"
	       sh "sudo docker run -itdp 8085:80 -v my-volume-4:/usr/local/apache2/htdocs --name container-4 httpd"
	      
      }
    }
  }
}
