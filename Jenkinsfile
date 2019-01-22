@Library('jenkinsLib') _

node {

  stage('Init') {
    // hello(debug: false)
    // config.debug = true
    // hello(config)
    // config.message = "toto"
    // hello(config)
    //

    def config = [:]
    testFunction(config)
    testFunction()

    //
    // // Show git informations
    // // Set display name
    // initialize()
  }

  // stage('Security') {
  //
  // }


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

def testFunction(Map config = [:]) {
  config.debug = config.debug ?: false

  // if (!config.containsKey("debug")) {
  //   config.debug = false
  // }
  echo String.valueOf(config.debug)
}
