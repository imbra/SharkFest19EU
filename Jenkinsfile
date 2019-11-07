pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    tshark -i lo0 -c 1000 -T ek -Y "amqp"> /Users/imbra/Downloads/packetsTest.json
                    curl -s -H "Content-Type: application/x-ndjson" -XPOST "localhost:9200/packets-test/_bulk" --data-binary "@/Users/imbra/Downloads/packetsTest.json";
                '''
            }
        }
    }
}