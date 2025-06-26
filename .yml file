# .jenkins-pipeline.yml
pipeline:
  agent any

  tools:
    maven: 'Maven3'   # use same name you added in Jenkins global tools

  stages:
    - stage: Checkout Code
      steps:
        - checkout scm

    - stage: Build and Run Tests
      steps:
        - sh 'mvn clean test -DsuiteXmlFile=testng.xml'


    - stage: Publish Report
      steps:
        - junit 'test-output/testng-results.xml'

  post:
    always:
      mail:
        to: 'kamasanikaveri@gmail.com'
        subject: "Selenium Test Results"
        body: |
          Jenkins Job Completed
          Please check the build status and results in Jenkins dashboard.
