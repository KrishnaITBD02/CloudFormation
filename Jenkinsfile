pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
        AWS_ACCESS_KEY_ID = credentials('AKIASVJTVY6MNN3FEDGC')
        AWS_SECRET_ACCESS_KEY = credentials('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')
        STACK_NAME = 'test_stack'
        TEMPLATE_FILE = './cloudformation-template.yml'
    }

    stages {
        stage('Deploy CloudFormation Stack') {
            steps {
                script {
                    // Use AWS CLI to create the CloudFormation stack
                    sh "aws cloudformation create-stack --stack-name ${STACK_NAME} --template-body file://${TEMPLATE_FILE} --capabilities CAPABILITY_IAM"
                }
            }
        }
    }
}
