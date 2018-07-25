node() {
	def j =1 
	promoteToNext(j)  
	
	stage("Green To Node 1"){      
          		promoteToNext(j+1)
	        } // stage branch code scan
     
	stage("Green To Node 2"){   

	        } // stage branch build and unit test
     	} // node default build server

def promoteToNext(i) {
	stage("Proceed to Deploy ?"){
		node(){
	    // we need a first milestone step so that all jobs entering this stage are tracked an can be aborted if needed
	    milestone i
	    // time out manual approval after ten minutes
	    timeout(time: 10, unit: 'MINUTES') {
	        input message: "Promote to next environment ?"
	    }
	    // this will kill any job which is still in the input step
	   milestone i+1
	   } // node build server
   }// stage promote?
} // manual promotion
