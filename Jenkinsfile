pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment {
    PATH = "/opt/apache-maven-3.9.9/bin:$PATH"
}
    stages {
        stage("build") {
            steps {
                echo "-------------- build started ---------------"
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                echo "-------------- build completed ---------------"
            }
        }

        stage("test") {
            steps {
                echo "-------------- unit tests started ---------------"
                sh 'mvn surefire-report:report'
                echo "-------------- unit tests completed ---------------"
            }
        }
    }
}
