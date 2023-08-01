pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
        STACK_NAME = 'test_stack'
        TEMPLATE_FILE = './cloudformation-template.yml'
 	AWS_ACCESS_KEY_ID = credentials('SecretId')
        AWS_SECRET_ACCESS_KEY = credentials('Key')
    }

   
    stages {
        stage('Deploy CloudFormation Stack') {
            steps {
                withCredentials([
                    string(credentialsId: 'MyAWSAccessKeyId', variable: 'AWS_ACCESS_KEY_ID'),
                    string(credentialsId: 'MyAWSAccessKeySecret', variable: 'AWS_SECRET_ACCESS_KEY')
                ]) {
                    script {
                        sh "aws cloudformation create-stack --stack-name ${STACK_NAME} --template-body file://${TEMPLATE_FILE} --capabilities CAPABILITY_IAM --region ${AWS_DEFAULT_REGION}"
                    }
                }
            }
        }
    }
}
