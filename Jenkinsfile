#! /usr/bin/env groovy

pipeline {

  agent any
  environment {
    SPECTRAL_DSN = 'https://spu-802f11247c654067be46822a73c34584@spectral-eu.checkpoint.com'
  }
  stages {
    stage('install Spectral') {
      steps {
        sh "curl -L 'https://spectral-eu.checkpoint.com/latest/x/sh?key=spu-802f11247c654067be46822a73c34584' | sh"
      }
    }
    stage('scan for issues') {
      steps {
        sh "$HOME/.spectral/spectral scan --fail-on-error  --include-tags base,audit"
      }
    }
  }
}
