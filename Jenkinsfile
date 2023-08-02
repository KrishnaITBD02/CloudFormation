pipeline {
    agent any

    environment {
        STACK_NAME = 'Splunk' // Change this to the desired stack name
        TEMPLATE_FILE = './cloudformation_script.yml' // Change this to the path of your CloudFormation template
    }

    stages {
        stage('Deploy CloudFormation Stack') {
            steps {
                script {
                    // Create or update the CloudFormation stack
                    sh "aws cloudformation deploy --stack-name $STACK_NAME --template-file $TEMPLATE_FILE --region 'us-east-1'"
                }
            }
        }
    }
}
