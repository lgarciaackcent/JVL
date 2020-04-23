
import groovy.json.JsonSlurper





static Object getJson( Object script, String path ) {

def k_username = "username"; def v_username = "admin";
def k_passwd = "password"; def v_passwd = "HVAk3Ps^/x8WFYAZ(c3)7K.,|";
def k_grant_type = "grant_type"; def v_grant_type = "password";
def k_scope = "scope"; def v_scope = "cxarm_api";
def k_client_id = "client_id"; def v_client_id = "resource_owner_client";
def k_client_secret = "client_secret"; def v_client_secret = "014DF517-39D1-4453-B7B3-9930C563627C";


	String urlParameters  = k_username + "=" + v_username + "&" +
							k_passwd + "=" + v_passwd + "&" +
							k_grant_type + "=" + v_grant_type + "&" +
							k_scope + "=" + v_scope + "&" +
							k_client_id + "=" + v_client_id + "&" +
							k_client_secret + "=" + v_client_secret;

    byte[] postData = urlParameters.getBytes("utf-8");
    int    postDataLength = postData.length;


	script.info( script, "getJson" ) ;
	script.info( script, path ) ;
	
	String apiString = path;
	
	script.info( script, "Empezamos al inicio del try" ) ;
	try {
		URL apiURL = new URL( apiString );
		HttpURLConnection myURLConnection = (HttpURLConnection) apiURL.openConnection();
		myURLConnection.setDoOutput(true);
		myURLConnection.setRequestMethod( "POST" );
		myURLConnection.setRequestProperty( "Content-Type", "application/x-www-form-urlencoded"); 
		myURLConnection.setRequestProperty( "Content-Length", Integer.toString( postDataLength ));
    
    	DataOutputStream wr = new DataOutputStream( myURLConnection.getOutputStream() );
   		wr.write( postData );
	} catch ( ex ) {   
		script.info( script, "Excepcion al escribir" );
		script.info( script, ex.getMessage() );
	}
	script.info( script, "Acabamos el try" ) ;
	
	return null;
	
	//myURLConnection.setRequestProperty("Content-Type", "application/json; utf-8");
	//myURLConnection.setRequestProperty("Accept", "application/json");
	
	String jsonInputString = "{\"username\": \"admin\", \"password\": \"HVAk3Ps^/x8WFYAZ(c3)7K.,|\"\"}";
	//String urlParameters  = "username=admin&password=HVAk3Ps^/x8WFYAZ(c3)7K.,|&param3=c";
	
	script.info( script, "Post" ) ;						
	script.info( script, urlParameters ) ;	
							
	OutputStream os = myURLConnection.getOutputStream();
    byte[] input = jsonInputString.getBytes("utf-8");
    script.info( script, "Antes de setRequestProperty" ) ;	
    script.info( script, "Despues  de setRequestProperty" ) ;
    
    try {
    	script.info( script, "A escribir" ) ;	
    	os.write(postData, 0, postData.length);           
	} catch ( ex ) {   
		script.info( script, "Excepcion al escribir" );
		script.info( script, ex.getMessage() );
	}
	
	script.info( script, "getJson despues" ) ;
	
	
	return new JsonSlurper().parse(myURLConnection.inputStream);
	
}

def info(script,msg){
        script.echo "[INFO] ${msg}" 
    }
    

def getKK( script, pp ) {
	info( script, pp ) ;
	//this.echo "hola peroal" 
	//[INFO] ${msg}" 
	//info(this,"SOME VERY USEFUL INFORMATION"); 
	return "hola caracola";
}


static String getPP( Object script, String pp ) {
	script.info( script, pp ) ;
	//this.echo "hola peroal" 
	//[INFO] ${msg}" 
	//info(this,"SOME VERY USEFUL INFORMATION"); 
	return "hola caracola";
}


static String getModelId( Object script, String modelName ) {

	String getTokenURL = "https://checkmarx.ackcent.com/cxrestapi/auth/identity/connect/token";

	script.info( script, "----T2" );
	
	try {
    
    	//def json = getJson( "https://checkmarx.ackcent.com/xxxx" ); // + java.net.URLEncoder.encode( modelname, "UTF-8" );
    	script.info( script,  "----HOLA" );
    	def json = getJson( script, getTokenURL );
    	script.info( script,  "----HOLA2" );
     	return json.access_token;
    
	} catch ( e ) {   
		script.info( script, "Excepcion" );
		script.info( script, e.getMessage());
		script.info( script, e.printStackTrace() );
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
                
                	println( "----T0" );
                	info(this, "hola perola");
                	def res = getModelId(this, "pepe" )
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