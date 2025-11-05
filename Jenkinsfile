 pipeline { 
        agent any 
         environment {
             APP_ENV = "staging"
             VERSION = "1.0.${BUILD_NUMBER}"
                    }
              parameters { 
                choice(name: 'DEPLOY_ENY', choices: ['staging', 'production'], description: 'Select deployment environment')
                       }
             stages {
                     stage('Build') {
                      steps {
                         echo"Building version ${version} for ${APP_ENV} environment"
                        }

               }
                   stage('Test'){
                    echo "Running Tests"
                       }
                   stage("Deploy"){
                    echo"Deploying to ${param.DEPLOY.ENV} environment"
                          }
             }
     }
post {
success {
   echo "Build success"
         }
failure {
    echo "Build Failed"}
always {
   echo "Pipeline Completed (success or fail}"   
}
