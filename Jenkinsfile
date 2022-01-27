node{
// demo
   stage('SCM Checkout'){
     git branch: 'maven', url: 'https://github.com/vikash-kumar01/CICD_Java_gradle_application.git'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'maven-5', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   
   stage('SonarQube Analysis') {
        def mvnHome =  tool name: 'maven-5', type: 'maven'
        withSonarQubeEnv('sonarserver') { 
          sh "${mvnHome}/bin/mvn sonar:sonar"
        }
    }

}
