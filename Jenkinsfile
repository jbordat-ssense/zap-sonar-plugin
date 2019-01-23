@Library('jenkinsLib') _

node {

  def config = [
    debug:true,
    mvn_command_line: "clean package -DskipTests"
  ]

  stage('Init') {
    // Show git informations
    // Set display name
    initialize(config)
  }

  stage('Build') {
    // Build maven
    mvn(config)
  }

  stage('Security') {
    // Lanch Sonar Qube analysis
    qaAnalysis(config)
  }


  //
  // stage('Repository') {
  //
  //   // git branch: 'master', url: "${git_url}"
  //
  //   def shortCommit = pipelineLibs.getShortCommit()
  //   def commitChangeset = pipelineLibs.getCommitChangeset()
  //
  //   pipelineLibs.setBuildName("v1.0")
  //
  // }
  //
  // stage('Build') {
  //   pipelineLibs.sayHello()
  // }
  //
  // stage('OWASP & Sonar') {
  //   // pipelineLibs.owaspDependencyCheck(pipelineJdk, pipelineMvn)
  //   // pipelineLibs.sonarAnalysis()
  // }

}
