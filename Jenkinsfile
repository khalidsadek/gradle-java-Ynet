pipeline{
    agent any

	
    stages{
        stage('Git Clone'){
            steps{
                git branch: 'master', url:'https://github.com/khalidsadek/gradle-java-Ynet.git'
            }
         }
        stage('Build Gradle') {
// 		 options {
//                 timeout(time: 3, unit: "MINUTES")
//             }
            steps {
                    sh '''
		    	cd gradle-yn
		    	
			    gradle build
			        '''
                // script{

		    	// //cd gradle-yn
		    	// //chmod +x gradlew
			    // "./gradlew build"

                // }

			    }
        }
        // stage('Run Jar File') {
        //     steps {
        //             sh 'java -jar build/libs/gradle-yn-1.0-SNAPSHOT.jar'
        //     }
        // }

    //   stage('Run'){
    //         steps{
    //      //   sh 'gradle-yn'    
	// 	    sh 'gradle run'
            
	//     }
    //     }



    //     stage('Archive The Artifacts'){
    //         steps{
    //             archiveArtifacts artifacts: '**/output.html', followSymlinks: false
    //         }
    //     }


    }

    post{
        success{
//           	 options {
//                 timeout(time: 3, unit: "MINUTES")
//             }
                   sh 'java -jar build/libs/gradle-yn-1.0-SNAPSHOT.jar'
            
        
           // archiveArtifacts artifacts: '**/*.html', onlyIfSuccessful: true
        }
    }



}
