pipeline{
   agent{label 'user'}
   
   stages{
      stage('Checkout Stage'){
	     steps{
		    echo 'Data is fetched successfully from github.com'
		 }
   }
   
   stage('Approval for Dev'){
            steps{
                
                //----------------send an approval prompt-------------
                script {
                   env.DEV = input message: 'Please enter input',
                   parameters: [choice(name: 'Deploy?', choices: 'no\nyes', description: 'Choose "yes" if you want to give approval for dev')]
                       }
                //-----------------end approval prompt------------
            }
    }
   
   
    stage('DEV stage'){
	     when {
                environment name:'DEV', value: 'yes'
         }
	     steps{
		    
		    echo 'Dev stage successfully exceuted'
		 }
   }
   
   
   stage('Approval for QA'){
            steps{
                
                //----------------send an approval prompt-------------
                script {
                   env.QA = input message: 'Please enter input',
                   parameters: [choice(name: 'Deploy?', choices: 'no\nyes', description: 'Choose "yes" if you want to give approval for qa')]
                       }
                //-----------------end approval prompt------------
            }
    }
   
   
    stage('QA stage'){
	     when {
                environment name:'QA', value: 'yes'
         }
	     steps{
		    
		    echo 'QA stage successfully exceuted'
		 }
   }
   
   
   
   stage('Approval for UAT'){
            steps{
                
                //----------------send an approval prompt-------------
                script {
                   env.UAT = input message: 'Please enter input',
                   parameters: [choice(name: 'Deploy?', choices: 'no\nyes', description: 'Choose "yes" if you want to give approval for uat')]
                       }
                //-----------------end approval prompt------------
            }
    }
   
   
    stage('UAT stage'){
	     when {
                environment name:'UAT', value: 'yes'
         }
	     steps{
		    
		    echo 'UAT stage successfully exceuted'
		 }
   }
   
   
      stage('Approval for PROD'){
            steps{
                
                //----------------send an approval prompt-------------
                script {
                   env.PROD = input message: 'Please enter input',
                   parameters: [choice(name: 'Deploy?', choices: 'no\nyes', description: 'Choose "yes" if you want to give approval for prod')]
                       }
                //-----------------end approval prompt------------
            }
    }
   
   
    stage('PROD stage'){
	     when {
                environment name:'PROD', value: 'yes'
         }
	     steps{
		    
		    echo 'PROD stage successfully exceuted'
		 }
   }
   
   
   
   }
   
   post{
      success{
	     echo 'Successfully excuted'
	  }
	  
	  failure{
	     echo 'Fail....Please check again!!'
	  }
   }
}
