pipeline{
    agent { label 'slave' } 

	
    stages{
        stage('Git Clone'){
            steps{
                git branch: 'master', url:'https://github.com/khalidsadek/gradle-java-Ynet.git'
            }
         }
        stage('Build Gradle') {
		//  options {
        //         timeout(time: 7, unit: "MINUTES")
        //     }
            steps {
                    sh '''
		    	cd gradle-yn
                gradle clean
			    gradle build
			        '''
		    	// //cd gradle-yn
		    	// //chmod +x gradlew
			    // "./gradlew build"    chmod 755 ./gradlew
			    }
        }
        stage('Run Jar File') {
            steps {
                    sh 'java -jar **/build/libs/gradle-yn-1.0-SNAPSHOT.jar'
            }
        }

    //   stage('Run'){
    //         steps{
    //      //   sh 'gradle-yn'    
	// 	    sh 'gradle run'
            
	//     }
    //     }


        stage('Archive The Artifacts'){
            steps{
                archiveArtifacts artifacts: '**/*.html', followSymlinks: false
            }
        }

    }

    post{
        success{

            slackUploadFile filePath: 'output.html', initialComment: 'Here is RSS file '
            //    archiveArtifacts artifacts: '**/*.html', followSymlinks: false
    
           // archiveArtifacts artifacts: '**/*.html', onlyIfSuccessful: true
        }
    }



}
