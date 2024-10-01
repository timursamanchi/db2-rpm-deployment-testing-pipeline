pipeline {
    agent any
    stages {
        stage('Run Multiple Commands via SSH') {
            steps {
                sh '''
                    ssh -T -i /var/jenkins_home/.ssh/id_rsa -o StrictHostKeyChecking=no ec2-user@ip-172-31-4-105 <<EOF
                    echo "this is a test from Timur" > /var/jenkins_home/workspace/HSBC-BD2/ssh-db2-deployment
                    mkdir /home/ec2-user/my_new_directory
                    touch /home/ec2-user/my_new_directory/newfile2.txt
EOF
                '''
            }
        }
        stage('Install DB2') {
            steps {
                sh '''
                    echo "Building DB2 server deployment"
                    pwd
                    ssh -T -i /var/jenkins_home/.ssh/id_rsa -o StrictHostKeyChecking=no ec2-user@ip-172-31-4-105 <<EOF
                    cat /var/jenkins_home/workspace/HSBC-BD2/ssh-db2-deployment/my-new.txt
EOF
                '''
            }
        }
    }
}
