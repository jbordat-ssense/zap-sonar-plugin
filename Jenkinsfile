@Library('jenkinsLib') _

def config = [
  debug:true,
  mvn_command_line: "clean package -DskipTests",
  project_name: "MS-Demo-Test-Sample-Try",
  project_key: "ms-demo-test-sample-try",
  slack_message_version: 1
]

defaultPipeline(config) { context ->
  stage('Init') {
    // Show git informations
    // Set display name
    initialize(config)
  }
  stage('Build') {
    // Build maven
    mvn(config)
  }
  stage('Dependency Check') {
    // Lanch Sonar Qube analysis
    dependencyCheck(config)
  }
  stage('QA') {
    // Lanch Sonar Qube analysis
    qaAnalysis(config)
  }
  
}
