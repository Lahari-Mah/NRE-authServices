pipeline
{
  agent any
  stages{
    stage('Build Application'){
      steps{
    		sh 'mvn clean install -DskipTests'
    	}
    }
    
    stage('Deploy Application to MuleSoft CloudHub'){
     steps{
    		sh 'mvn package deploy -DmuleDeploy -DskipTests -Dmule.version=4.3.0 -Danypoint.username=lahariteja -Danypoint.password=Mah@987654321 -Denv=Sandbox -Dappname=NRE-authServices'
    	}
    }
    
    stage('Perform Regression Testing'){
      steps{
    		sh 'newman run /Users/rm/Desktop/NjcLabs/newman/getUserServices.postman_collection.json'
    	 }
    }
  }
}