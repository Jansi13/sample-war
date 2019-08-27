pipeline {
  

  agent { label 'master' }
  
  stages {

   stage("cloning from the GIT") {
	steps {
	echo "cloning from git "
	}


   }

   stage("build using maven")
   {
	steps {
	echo "build using maven"
	      }
		  		
   }

   stage("results")
   {
	steps {
	echo "results stage"
		}
   }

}
  } 
