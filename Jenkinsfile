
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
                echo "Hello World"
                //bat( script: "C:/LGV/tmp/lgv.bat", returnStatus=false )
                //bat 'C:/LGV/tmp/lgv.bat'
				//bat 'C:/LGV/Software/apache-maven-3.6.3-bin/apache-maven-3.6.3/bin/mvn clean compile'
				withMaven(maven: 'Maven_home', jdk: 'openjdk-8u242-b08') {
                    bat 'mvn clean compile'
                }
            }
        }
        
        stage ('Checkmarx Scan Stage') {

            steps {
                echo "Hello World - Ackcent"
				//bat 'C:/LGV/Software/apache-maven-3.6.3-bin/apache-maven-3.6.3/bin/mvn clean compile'
				
                step([$class: 'CxScanBuilder', 
                comment: '110004 JVL2', credentialsId: '', excludeFolders: '', excludeOpenSourceFolders: '', exclusionsSetting: 'global', failBuildOnNewResults: false, failBuildOnNewSeverity: 'HIGH', 
                filterPattern: '''!**/_cvs/**/*, !**/.svn/**/*,   !**/.hg/**/*,   !**/.git/**/*,  !**/.bzr/**/*, !**/bin/**/*,
!**/obj/**/*,  !**/backup/**/*, !**/.idea/**/*, !**/*.DS_Store, !**/*.ipr,     !**/*.iws,
!**/*.bak,     !**/*.tmp,       !**/*.aac,      !**/*.aif,      !**/*.iff,     !**/*.m3u, !**/*.mid, !**/*.mp3,
!**/*.mpa,     !**/*.ra,        !**/*.wav,      !**/*.wma,      !**/*.3g2,     !**/*.3gp, !**/*.asf, !**/*.asx,
!**/*.avi,     !**/*.flv,       !**/*.mov,      !**/*.mp4,      !**/*.mpg,     !**/*.rm,  !**/*.swf, !**/*.vob,
!**/*.wmv,     !**/*.bmp,       !**/*.gif,      !**/*.jpg,      !**/*.png,     !**/*.psd, !**/*.tif, !**/*.swf,
!**/*.jar,     !**/*.zip,       !**/*.rar,      !**/*.exe,      !**/*.dll,     !**/*.pdb, !**/*.7z,  !**/*.gz,
!**/*.tar.gz,  !**/*.tar,       !**/*.gz,       !**/*.ahtm,     !**/*.ahtml,   !**/*.fhtml, !**/*.hdm,
!**/*.hdml,    !**/*.hsql,      !**/*.ht,       !**/*.hta,      !**/*.htc,     !**/*.htd, !**/*.war, !**/*.ear,
!**/*.htmls,   !**/*.ihtml,     !**/*.mht,      !**/*.mhtm,     !**/*.mhtml,   !**/*.ssi, !**/*.stm,
!**/*.stml,    !**/*.ttml,      !**/*.txn,      !**/*.xhtm,     !**/*.xhtml,   !**/*.class, !**/*.iml, !Checkmarx/Reports/*.*''', 
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