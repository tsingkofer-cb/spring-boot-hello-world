#!/usr/bin/env groovy
@Library('boxboat-dockhand')
@Library('tsingkofer-cb-lib')
import com.boxboat.jenkins.pipeline.build.*

def build = new BoxBuild()
pipeline {
  options {
    disableConcurrentBuilds()
    buildDiscarder(logRotator(numToKeepStr: '100'))
  }
  agent {
    kubernetes(tyAgentConfig())
  }

  stages {
    stage('wrapper'){
      steps {
        script {
          build.wrap{
            sh 'sleep 60'
          }
        }
      }
    }
  }
}
