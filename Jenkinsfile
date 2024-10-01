pipeline {
    agent any
    stages {
        stage('Run Multiple Commands via SSH') {
            steps {
                sh '''
                    ssh -T -i /var/jenkins_home/.ssh/id_rsa -o StrictHostKeyChecking=no ec2-user@ip-172-31-4-105 <<EOF
                    echo "this is a test from Timur" > /home/ec2-user/my-new.txt
                    mkdir /home/ec2-user/my_new_directory
                    touch /home/ec2-user/my_new_directory/newfile2.txt
EOF
                '''
            }
        }
    }
}
