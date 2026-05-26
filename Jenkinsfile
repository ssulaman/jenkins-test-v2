pipeline {
agent any

```
stages {

    stage('Checkout Info') {
        steps {
            echo 'HELLO FROM PIPELINE HI SULAMAN!!!!!'

            sh '''
                whoami
                hostname
                pwd
                ls -la
            '''
        }
    }

    stage('Install Dependencies') {
        steps {
            sh '''
                apt-get update

                apt-get install -y \
                    gcc \
                    make \
                    libpcre3 \
                    libpcre3-dev \
                    zlib1g \
                    zlib1g-dev \
                    libssl-dev
            '''
        }
    }

    stage('Build NGINX') {
        steps {
            sh '''
                cd nginx-1.30.2

                chmod +x configure

                ./configure

                make
            '''
        }
    }

    stage('Verify Build') {
        steps {
            sh '''
                cd nginx-1.30.2

                echo "=== OBJS FOLDER ==="

                ls -la objs

                echo "=== CHECK NGINX BINARY ==="

                file objs/nginx
            '''
        }
    }

    stage('Start NGINX') {
        steps {
            sh '''
                cd nginx-1.30.2

                chmod +x objs/nginx

                ./objs/nginx
            '''
        }
    }

    stage('Check Running Process') {
        steps {
            sh '''
                ps aux | grep nginx || true
            '''
        }
    }

    stage('Test NGINX') {
        steps {
            sh '''
                curl http://localhost || true
            '''
        }
    }
}

post {
    success {
        echo 'NGINX BUILD AND START SUCCESSFUL'
    }

    failure {
        echo 'PIPELINE FAILED'
    }
}
```

}
