#!groovy
import groovy.json.JsonSlurperClassic
node {

    def SF_CONSUMER_KEY_SIT='3MVG9rnryk9FxFMWvsjK.03bE09RtFHgM3MMOMe_0xG.eYirB1cxKpeubG_aj26VLp8ps6ag8ecMjzw1o6HIF'
    def SF_CONSUMER_KEY_DEV='3MVG9rnryk9FxFMVMSbFLvWZPBCikI3muBc.3ZbHsLZIrHWFN7ywNz3xy0N3sU0jkNENKdVOnI_npCJ8NGKX7'
    def SF_USERNAME_SIT='dmahato@deloitte.sit'
    def SF_USERNAME_DEV='dmahato@deloitte.com.leaddev'
    def SERVER_KEY_CREDENTIALS_ID='5ea9e40b-16a7-4df3-8caf-7573d80e2482'
    def SF_INSTANCE_URL = 'https://test.salesforce.com'

    

    def toolbelt = tool 'toolbelt'
   
	

      withCredentials([file(credentialsId: SERVER_KEY_CREDENTIALS_ID, variable: 'server_key_file')]) {
	//stages {
	    
        stage('Installation') {
          
         // println ('Inside Installation Stage')
               
		    rc = bat returnStatus: true, script: "\"${toolbelt}\" force:auth:jwt:grant --clientid ${SF_CONSUMER_KEY_SIT} --username ${SF_USERNAME_SIT} --jwtkeyfile \"${server_key_file}\" --setalias AavasDEV --instanceurl ${SF_INSTANCE_URL}"
		    rc = bat returnStatus: true, script: "\"${toolbelt}\" force:auth:jwt:grant --clientid ${SF_CONSUMER_KEY_DEV} --username ${SF_USERNAME_DEV} --jwtkeyfile \"${server_key_file}\" --setalias AavasSIT --instanceurl ${SF_INSTANCE_URL}"		    
		    
            bat returnStatus: true, script: "\"${toolbelt}\" force:org:list"

        }
	    
	    

        

//}
}
 
}
