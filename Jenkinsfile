pipeline {
  agent any
  parameters {
    string(name: 'RELEASE_VERSION', defaultValue: '0.0.0-develop-000', description: 'Release Version')
  }
  environment {
    //SCHEDULER_IMAGE_PATH = "$PIPELINES_REGISTRY_URL/$SCHEDULER_IMAGE"
    RELEASE_VERSION = "0.0.0-develop-000"
  }

  stages {
    stage('Install and Verify Dependencies') {
      steps {
        echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
        echo "${params.ReleaseVersion}"
      }
    }
    stage('Build Docker Image for Scheduler service') {
      steps {
        echo "Building docker image for Scheduler services"
      }
    }
    stage('Running tests for all services') {
      steps {
        echo "Running tests"
      }
    }
    stage('Push Docker Images to ECR') {
      steps {
        echo "Pushing docker images to ECR"
      }
    }

    stage('Trigger deployments') {
      steps {
        echo "Trigger Deployment"
      }
    }
  }

  post {
    success {
      echo "CI script Succeeded...."
    }
    failure {
      echo "CI script failed...."
    }
  }
}
