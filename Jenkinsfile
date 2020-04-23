
import groovy.json.JsonSlurper



static String getModelId( String modelName ) {

try {
    
    def json = getJson( "https://checkmarx.ackcent.com/xxxx" ); // + java.net.URLEncoder.encode( modelname, "UTF-8" );
     retrurn json.kk;
    
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