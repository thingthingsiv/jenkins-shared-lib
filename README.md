Jenkins Shared Library
Overview
This repo contains a Jenkins shared library with reusable pipeline functions to simplify Jenkinsfiles.

Functions
setScriptPermission(List scripts): Adds executable permission to scripts.

runDeployScript(String scriptPath): Runs a deployment script.

Usage
Add this library to Jenkins (name: my-shared-lib, repo: https://github.com/thingthingsiv/jenkins-shared-lib.git, branch: main).

In your Jenkinsfile:

groovy
Copy
Edit
@Library('my-shared-lib@main') _

pipeline {
  agent any
  stages {
    stage('Set Permission') {
      steps { script { setScriptPermission(['deploy.sh']) } }
    }
    stage('Deploy') {
      steps { script { runDeployScript('./deploy.sh') } }
    }
  }
}

Sivthingthing

