@Library('jenkinsLib@feat/DEVOPS-1079_auto_apps_security_scans') _

node {

  def config = [
    debug:true,
    mvn_command_line: "clean package -DskipTests",
    project_name: "MS-Sample",
    project_key: "ms-sample",
  ]

  try {

    config.step = 1
    slack(config)

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

    // stage('End') {
    //   gitshortcommit = "${env.GIT_COMMIT[0..7]}"
    //   echo env
    // }

    currentBuild.result = "SUCCESS"
    config.step = 3
    slack(config)
  } catch (org.jenkinsci.plugins.workflow.steps.FlowInterruptedException ex) {
  currentBuild.result = "ABORTED"
    config.step = 3
    slack(config)
  } catch (Exception ex) {
    currentBuild.result = "FAILURE"
    config.step = 3
    slack(config)
    println(ex.toString());
    println(ex.getMessage());
    println(ex.getStackTrace());
  }

}
