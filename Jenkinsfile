
import groovy.json.JsonSlurper

def info(script,msg){
        script.echo "[INFO] ${msg}" 
    }

static Object getJsonReportId( Object script, String path, String token ) {

	script.info( script, "getJsonReportId" ) ;
	script.info( script, path ) ;
	
	String apiString = path;
	
	script.info( script, "Empezamos al inicio del try" ) ;
	try {
		URL apiURL = new URL( apiString );
		HttpURLConnection myURLConnection = (HttpURLConnection) apiURL.openConnection();
		myURLConnection.setDoOutput(true);
		myURLConnection.setRequestMethod( "POST" );
    	myURLConnection.setRequestProperty( "Authorization", "Bearer " + token );
    	myURLConnection.setRequestProperty("Content-Type", "application/json; utf-8");
    	myURLConnection.setRequestProperty("Accept", "application/json" );
    	myURLConnection.setDoOutput(true);
    	
    	//JSONObject cred = new JSONObject();
    	//def jsonSlurper = new JsonSlurper()
		//def object = jsonSlurper.parseText('{ "report Type": "XML" }
		def jsonSlurper = new JsonSlurper()
		def jsonInput = jsonSlurper.parseText '''
    		{ 
    		"reportType": "XML",
      		"scanId": 1070194
    		}'''
    
    	def jsonInput1 = JsonOutput.toJson([reportType: 'XML', scanId: 1070194])
    	
    	//String jsonInputString = "{" + "reportType: " + "XML" + "scanId: 1070194" + "}";
    	String jsonInputString = jsonInput1.toString();
    	script.info( script, "jsonInput [" + jsonInput1 + "]" ) ;
    	script.info( script, "jsonInputStrin ["  + jsonInputString + "]" ) ;
    	
    	OutputStream os = myURLConnection.getOutputStream();
    	//byte[] input = jsonInputString.getBytes("utf-8");
    	byte[] input = jsonInput1.getBytes("utf-8");
    	os.write(input, 0, input.length);           
    	  	
   		script.info( script, "Retornamos en try" ) ;
   		return new JsonSlurper().parse(myURLConnection.inputStream);
	} catch ( ex ) {   
		script.info( script, "Excepcion al escribir" );
		script.info( script, ex.getMessage() );
		return null;
	}

	
}




static Object getJsonPolicy( Object script, String path, String token ) {

	script.info( script, "getJsonPolicy" ) ;
	script.info( script, path ) ;
	
	String apiString = path;
	
	script.info( script, "Empezamos al inicio del try" ) ;
	try {
		URL apiURL = new URL( apiString );
		HttpURLConnection myURLConnection = (HttpURLConnection) apiURL.openConnection();
		myURLConnection.setDoOutput(true);
		myURLConnection.setRequestMethod( "GET" );
    	myURLConnection.setRequestProperty( "Authorization", "Bearer " + token );
    	myURLConnection.setRequestProperty("Accept", "application/json" );  	
   		script.info( script, "Retornamos en try" ) ;
   		return new JsonSlurper().parse(myURLConnection.inputStream);
	} catch ( ex ) {   
		script.info( script, "Excepcion al escribir" );
		script.info( script, ex.getMessage() );
		return null;
	}

	
}


static Object getJsonTokenSast( Object script, String path ) {

	def k_username = "username"; def v_username = "admin";
	def k_passwd = "password"; def v_passwd = "HVAk3Ps^/x8WFYAZ(c3)7K.,|";
	def k_grant_type = "grant_type"; def v_grant_type = "password";
	def k_scope = "scope"; def v_scope = "sast_rest_api";
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

	script.info( script, "getJsonToken" ) ;
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
   		script.info( script, "Retornamos en try" ) ;
   		return new JsonSlurper().parse(myURLConnection.inputStream);
	} catch ( ex ) {   
		script.info( script, "Excepcion al escribir" );
		script.info( script, ex.getMessage() );
		return null;
	}

	
}


static Object getJsonToken( Object script, String path ) {

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

	script.info( script, "getJsonToken" ) ;
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
   		script.info( script, "Retornamos en try" ) ;
   		return new JsonSlurper().parse(myURLConnection.inputStream);
	} catch ( ex ) {   
		script.info( script, "Excepcion al escribir" );
		script.info( script, ex.getMessage() );
		return null;
	}

	
}

    
static String getReportId( Object script, String token, String projectId ) {

	String getReportIdURL = "https://checkmarx.ackcent.com/reports/sastScan";
	
	try {  
    	def json = getJsonReportId( script, getReportIdURL, token );
    	script.info( script, "getReportId json" + json );
    	return json.reportId;
    
	} catch ( e ) {   
		script.info( script, "Excepcion getReportId" );
		script.info( script, e.getMessage());
		script.info( script, e.printStackTrace() );
		e.printStackTrace();         
      return "Error del copon";          
   	}
   	
}

static String getPolicy( Object script, String token, String projectId ) {

	String getPolicyURL = "http://checkmarx.ackcent.com:8080/cxarm/policymanager/projects/" + projectId + "/violations";
	
	try {  
    	def json = getJsonPolicy( script, getPolicyURL, token );
    	return json.violations;
    
	} catch ( e ) {   
		script.info( script, "Excepcion getPolicy" );
		script.info( script, e.getMessage());
		script.info( script, e.printStackTrace() );
		e.printStackTrace();         
      return "Error del copon";          
   	}
   	
}


static String getCnxTokenSast( Object script ) {

	String getTokenURL = "https://checkmarx.ackcent.com/cxrestapi/auth/identity/connect/token";
	
	try {  
    	def json = getJsonTokenSast( script, getTokenURL );
    	return json.access_token;
    
	} catch ( e ) {   
		script.info( script, "Excepcion" );
		script.info( script, e.getMessage());
		script.info( script, e.printStackTrace() );
		e.printStackTrace();         
      return "Error del copon";          
   	}
   	
}

static String getCnxToken( Object script ) {

	String getTokenURL = "https://checkmarx.ackcent.com/cxrestapi/auth/identity/connect/token";
	
	try {  
    	def json = getJsonToken( script, getTokenURL );
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
            	
            	//info(this, currentBuild.rawBuild.getLog(100) ); 
            	
          		
          		echo "Bye World - Ackcent"
          		
          			
            	script {
                
                	
                
                
                	def projectId = "40034";
                	
                	info(this, "Iniciando scan de " + projectId );

					def presetId = '110005';
				
				
					if ( true ) {
                	step([$class: 'CxScanBuilder', 
                		sastEnabled: true,
                	    incremental: false, 
                	    	fullScanCycle: 10, 
                	    waitForResultsEnabled: true,
                	    vulnerabilityThresholdEnabled: false,
                	    	highThreshold: 1, mediumThreshold: 2, lowThreshold: 5,
                	    	failBuildOnNewResults: false, failBuildOnNewSeverity: 'HIGH', 
                	    		vulnerabilityThresholdResult: 'FAILURE',
                	    projectName: 'JVL',
                		comment: 'INC JVL2',  
                		teamPath: 'CxServer\\SP\\Company\\Desarrollo',
                		preset: '{presetId}', 
                		excludeFolders: 'Reports, admin, vulnerability, target, hooks, .git, .settings, controller, WEB-INF, docs, images', excludeOpenSourceFolders: '', exclusionsSetting: 'job', 
                		includeOpenSourceFolders: '', osaArchiveIncludePatterns: '*.zip, *.war, *.ear, *.tgz', osaInstallBeforeScan: false, 
						credentialsId: '',
						password: '{AQAAABAAAAAQx9moxhCW9yxxy4RYWljNEQwm/xkawFV244zVHm+3OU8=}', 
						serverUrl: 'https://checkmarx.ackcent.com/', 
						sourceEncoding: '1', 
						username: ''])
					}
					
					
					def scanId = "";
					def ProjectId = "";
					def found = false;
          			
          			if (manager.logContains('.*Scan results location.*')) {
          			
          					// [Cx-Info]: Scan results location: https://checkmarx.ackcent.com//CxWebClient/ViewerMain.aspx?scanId=1070185&ProjectID=40034
          			
          					def matcher = manager.getLogMatcher('.*Scan results location: http.*scanId=(?<scanId>\\d{1,10})&ProjectID=(?<ProjectId>\\d{1,10}).*$')
							if(matcher?.matches()) {
								info(this, "MATCHER 0 " + matcher.group("scanId") );
								info(this, "MATCHER 1 " + matcher.group("ProjectId") );
								scanId = matcher.group("scanId");
								ProjectId = matcher.group("ProjectId");
								found = true;
    							//manager.addWarningBadge(matcher.group(1) )
    							//manager.createSummary("warning.gif").appendText(matcher.group(1), false, false, false, "red")
							}
          					
          			}
          			
          			if (found) {
          				info(this, "scanId [" + scanId + "]" );
          				info(this, "ProjectId [" + ProjectId + "]" );
          			} else {
          				info(this, "scanId & ProjectId not found." );
          			}
          			
          			
					
					def cnxToken = getCnxToken(this);
                	echo "TOKEN - [ ${cnxToken} ] "
                	def policy = getPolicy(this, cnxToken, projectId );
                	def String vacio = "[]";
                	echo "policy - [${policy}] ";
                	echo "vacio - [${vacio}] ";
                	if ( policy.toString() == vacio ) { 
                		info(this, "Se CUMPLE la Policy" );
                		info(this, "Setting build result to  " + "SUCESS" );
						currentBuild.result = 'SUCCESS';
                	} else {
                		info(this, "Se INCUMPLE la Policy" );
                		info(this, "Setting build result to  " + "FAILURE" );
                		currentBuild.result = 'FAILURE';
                	}     	
                	
                	def cnxToken_sast = getCnxTokenSast(this);
                	echo "TOKEN SAST - [ ${cnxToken_sast} ] "
                	def reportId = getReportId(this, cnxToken_sast, projectId );
                	echo "reportId - [${reportId}] ";
                	
                	
                	info(this, "ADIOS" );
					
            	}
            	
            	
            	
            }
        }
	
    }
	
}