pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello world!"'
            }
        }
    }
}
node {

  def git_url = "ssh://git@gitlab/grdf-dev/sofitsso.git"
  def pipelineLibs
  def pipelineJdk
  def pipelineMvn

  stage('Init') {
    git branch: 'master', url: "ssh://git@gitlab/grdf-dev/jenkinslib.git"
    pipelineLibs = load('jenkinsLib.groovy')
  }

  stage('Repository') {

    // git branch: 'master', url: "${git_url}"

    def shortCommit = pipelineLibs.getShortCommit()
    def commitChangeset = pipelineLibs.getCommitChangeset()

    pipelineLibs.setBuildName("v1.0")

  }

  stage('Build') {
    pipelineLibs.sayHello()
  }

  stage('OWASP & Sonar') {
    // pipelineLibs.owaspDependencyCheck(pipelineJdk, pipelineMvn)
    // pipelineLibs.sonarAnalysis()
  }

}
