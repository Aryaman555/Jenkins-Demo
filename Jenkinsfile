pipeline {
    agent any

    stages {
        stage('Stage 1: Restore Dependencies') {
            steps {
                echo 'Stage 1: Restore Dependencies'
                echo 'Description: Restoring NuGet packages for the C# .NET project.'
                echo 'Tool used: NuGet Package Manager'
            }
        }

        stage('Stage 2: Build') {
            steps {
                echo 'Stage 2: Build'
                echo 'Description: Building the C# .NET project.'
                echo 'Tool used: MSBuild'
            }
        }

        stage('Stage 3: Unit Tests') {
            steps {
                echo 'Stage 3: Unit Tests'
                echo 'Description: Running unit tests for the C# .NET project.'
                echo 'Tool used: NUnit or MSTest'
            }
            post {
                success {
                    emailext attachLog: true, body: "Stage 3: Unit Tests passed successfully.", subject: "Pipeline Notification: Stage 3 Passed", to: "dhiraryaman@gmail.com"
                }
                failure {
                    emailext attachLog: true, body: "Stage 3: Unit Tests failed. Please check the logs for details.", subject: "Pipeline Notification: Stage 3 Failed", to: "dhiraryaman@gmail.com"
                }
            }
        }

        stage('Stage 4: Code Analysis') {
            steps {
                echo 'Stage 4: Code Analysis'
                echo 'Description: Running code analysis for the C# .NET project.'
                echo 'Tool used: SonarQube or Roslyn Analyzers'
            }
        }

        stage('Stage 5: Security Scan') {
            steps {
                echo 'Stage 5: Security Scan'
                echo 'Description: Performing a security scan for the C# .NET project.'
                echo 'Tool used: SonarQube, OWASP Dependency Check, or other security scanners'
            }
            post {
                success {
                    emailext attachLog: true, body: "Stage 5: Security Scan passed successfully.", subject: "Pipeline Notification: Stage 5 Passed", to: "dhiraryaman@gmail.com"
                }
                failure {
                    emailext attachLog: true, body: "Stage 5: Security Scan failed. Please check the logs for details.", subject: "Pipeline Notification: Stage 5 Failed", to: "dhiraryaman@gmail.com"
                }
            }
        }

        stage('Stage 6: Publish Artifacts') {
            steps {
                echo 'Stage 6: Publish Artifacts'
                echo 'Description: Publishing artifacts for deployment.'
                echo 'Tool used: Jenkins Archive Artifacts'
            }
        }

        stage('Stage 7: Deploy to Test Environment') {
            steps {
                echo 'Stage 7: Deploy to Test Environment'
                echo 'Description: Deploying the C# .NET project to a test environment.'
                echo 'Tool used: Custom deployment scripts or tools like Octopus Deploy'
            }
        }

        stage('Stage 8: Integration Tests on Test Environment') {
            steps {
                echo 'Stage 8: Integration Tests on Test Environment'
                echo 'Description: Running integration tests on the deployed C# .NET project in the test environment.'
                echo 'Tool used: NUnit or MSTest, Selenium, or other integration testing frameworks'
            }
        }

        stage('Stage 9: Deploy to Production') {
            steps {
                echo 'Stage 9: Deploy to Production'
                echo 'Description: Deploying the C# .NET project to the production environment.'
                echo 'Tool used: Custom deployment scripts or tools like Octopus Deploy'
            }
        }
    }
}
