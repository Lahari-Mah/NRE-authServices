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
    		sh 'mvn package deploy -DmuleDeploy -DskipTests -Dmule.version=4.3.0 -Danypoint.username=lahariteja1 -Danypoint.password=Mah@987654321 -Denv=Sandbox -Dappname=NRE-userAuthServices -Dcloudhub.worker=Micro -Dapikey.id=2ebb6379710f4af39546584157fd896e -Dapikey.secret=7388e24F6C21434c8c269c1E0a81D110'
    	}
    }
    
    stage('Perform Regression Testing'){
      steps{
    		sh 'newman run /Users/rm/Desktop/NjcLabs/newman/postAuthorisation.postman_collection.json'
    	 }
    }
  }
}