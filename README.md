# Jenkins Shared Library

## Overview
This repository contains a Jenkins shared library with reusable pipeline functions to simplify Jenkins pipelines.

## Functions
- **setScriptPermission(List scripts)**: Adds executable permission to specified scripts.
- **runDeployScript(String scriptPath)**: Executes a deployment script.

## Usage
1. Add this library to Jenkins configuration:
   - Name: `my-shared-lib`
   - Repository URL: `https://github.com/thingthingsiv/jenkins-shared-lib.git`
   - Default branch: `main`

2. Use in your Jenkinsfile:

```groovy
@Library('my-shared-lib@main') _

pipeline {
  agent any
  stages {
    stage('Set Permission') {
      steps {
        script {
          setScriptPermission(['deploy.sh'])
        }
      }
    }
    stage('Deploy') {
      steps {
        script {
          runDeployScript('./deploy.sh')
        }
      }
    }
  }
}

by sivthingthing
