import groovy.json.JsonSlurperClassic

def jsonParse(def json) {
    new groovy.json.JsonSlurperClassic().parseText(json)
}
pipeline {
  agent { label 'master' }
  environment {
    appName = "variable" 
  }
  stages {

    stage("paso para rama devel"){
      when {
          branch 'devel' 
        }
      steps {
          script {			
                sh "paso 1 para devel"
        }
      }
    }
 stage("paso 1"){

      steps {
          script {			
           sh "hola mundo"
        }
      }
    }
  }
  post {
      always {          
          deleteDir()
      }
      success {
            sh "fase success"
        }
      unstable {
            sh "fase unstable"  
        }
      failure {
            sh "fase failure"
      }

  }
}  

