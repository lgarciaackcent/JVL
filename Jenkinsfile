
import groovy.json.JsonSlurper


def k_username = "username"; def v_username = "admin";
def k_passwd = "password"; def v_passwd = "HVAk3Ps^/x8WFYAZ(c3)7K.,|";
def k_grant_type = "grant_type"; def v_grant_type = "password";
def k_scope = "scope"; def v_scope = "cxarm_api";
def k_client_id = "client_id"; def v_client_id = "resource_owner_client";
def k_client_secret = "client_secret"; def v_client_secret = "014DF517-39D1-4453-B7B3-9930C563627C";



private static Object getJson( String path ) {

	String apiString = path;
	
	URL apiURL = new URL( apiString );
	HttpURLConnection myURLConnection = (HttpURLConnection) apiURL.openConnection();
	return new JsonSlurper().parse(myURLConnection.inputStream);
	
}

static String getModelId( String modelName ) {

	String getTokenURL = "https://checkmarx.ackcent.com/cxrestapi/auth/identity/connect/token";

	println( "----T1" );
	echo "----T1"

	try {
    
    	//def json = getJson( "https://checkmarx.ackcent.com/xxxx" ); // + java.net.URLEncoder.encode( modelname, "UTF-8" );
    	println( "----HOLA" );
    	def json = getJson( getTokenURL );
    	println( "----HOLA2" );
     	return json;
    
	} catch ( e ) {   
	
		e.printStackTrace();         
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
				
					if ( false ) {
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
	
}