pipeline {
   agent any
   parameters{
       string(name:'NAME', defaultValue:'my-app, description: 'name of the app')
       choice(name:'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'version of the app')
       booleanParam(name:'executeTests', defaultValues: true, description: 'check to execute tests')
  }
  stages {
     stages('build) {
         steps {
            echo 'building the application...'
            echo "built the $(NAME) app"
         }
    }
    stage('test') {
       when {
          expression {
               params.executeTests
          }
       }
       steps {
          echo 'testing the application...'
       }
   }
   stages('deploy') {
       steps {
           echo 'deploying the application...'
           echo "deployed version$(params.VERSION)"
       }
  }
