@Library('jenkinsLib@feat/DEVOPS-1079_auto_apps_security_scans') _

node {

  def config = [
    debug:true,
    mvn_command_line: "clean package -DskipTests",
  ]

  stage('Init') {
    // Show git informations
    // Set display name
    initialize(config)
  }
  //
  // stage('Build') {
  //   // Build maven
  //   mvn(config)
  // }
  //
  // stage('Dependency Check') {
  //   // Lanch Sonar Qube analysis
  //   dependencyCheck(config)
  // }
  //
  // stage('QA') {
  //   // Lanch Sonar Qube analysis
  //   qaAnalysis(config)
  // }

  stage('End') {
    gitshortcommit = "${env.GIT_COMMIT[0..7]}"
    echo env
  }

}
