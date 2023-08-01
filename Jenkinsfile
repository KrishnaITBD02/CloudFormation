pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
        STACK_NAME = 'test_stack'
        TEMPLATE_FILE = './cloudformation-template.yml'
    }

     stages {
        stage('Deploy CloudFormation Stack') {
            steps {
                script {
                    sh "aws cloudformation create-stack --stack-name ${STACK_NAME} --template-body file://${TEMPLATE_FILE}"
                }
            }
        }
    }
}
