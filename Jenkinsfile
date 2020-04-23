
import groovy.json.JsonSlurper


String k_username = "username"; String v_username = "admin";
String k_passwd = "password"; String v_passwd = "HVAk3Ps^/x8WFYAZ(c3)7K.,|";
String k_grant_type = "grant_type"; String v_grant_type = "password";
String k_scope = "scope"; String v_scope = "cxarm_api";
String k_client_id = "client_id"; String v_client_id = "resource_owner_client";
String k_client_secret = "client_secret"; String v_client_secret = "014DF517-39D1-4453-B7B3-9930C563627C";
String getTokenURL = "https://checkmarx.ackcent.com/cxrestapi/auth/identity/connect/token";



private static Object getJson( String path ) {

	String apiString = path;
	
	URL apiURL = new URL( apiString );
	HttpURLConnection myURLConnection = (HttpURLConnection) apiURL.openConnection();
	return new JsonSlurper().parse(myURLConnection.inputStream);
	
}

static String getModelId( String modelName ) {

	try {
    
    	//def json = getJson( "https://checkmarx.ackcent.com/xxxx" ); // + java.net.URLEncoder.encode( modelname, "UTF-8" );
    	def json = getJson( getTokenURL );
     	return json;
    
	} catch ( e ) {            
      return "Error del copon";          
   	}

}





pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                echo "Hello World Linux mvn"
                //bat( script: "C:/LGV/tmp/lgv.bat", returnStatus=false )
                //bat 'C:/LGV/tmp/lgv.bat'
				//bat 'C:/LGV/Software/apache-maven-3.6.3-bin/apache-maven-3.6.3/bin/mvn clean compile'
				//withMaven(maven: 'Maven_home', jdk: 'openjdk-8u242-b08') {
				withMaven() {
                    sh 'mvn clean compile'
                }
                //mvn clean compile
            }
        }
        
        stage ('Checkmarx Scan Stage x') {

            steps {
            
            	echo "Hello World - Ackcent"
            	script {
                
                	def res = getModelId( "pepe" );
                	echo "RETORNO - [ ${res} ] "
                
                
				//bat 'C:/LGV/Software/apache-maven-3.6.3-bin/apache-maven-3.6.3/bin/mvn clean compile'
				
                	step([$class: 'CxScanBuilder', 
                		comment: '110004 JVL2', credentialsId: '', excludeFolders: '', excludeOpenSourceFolders: '', exclusionsSetting: 'global', failBuildOnNewResults: false, failBuildOnNewSeverity: 'HIGH', 
						fullScanCycle: 10, 
						teamPath: 'CxServer\\SP\\Company\\Desarrollo', 
						includeOpenSourceFolders: '', osaArchiveIncludePatterns: '*.zip, *.war, *.ear, *.tgz', osaInstallBeforeScan: false, 
						password: '{AQAAABAAAAAQx9moxhCW9yxxy4RYWljNEQwm/xkawFV244zVHm+3OU8=}', 
						preset: '110004', 
						//preset: '36',
						projectName: 'JVL2', 
						sastEnabled: true, 
						serverUrl: 'https://checkmarx.ackcent.com/', 
						sourceEncoding: '1', 
						username: '', 
						vulnerabilityThresholdResult: 'FAILURE', 
						waitForResultsEnabled: true])
				
            	}
            	
            }
        }
	
    }
	
}