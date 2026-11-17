pipeline {
    agent any

    stages {
        stage('1. Checkout from Git') {
            steps {
                echo '=== משיך את הקוד האחרון מ-Git ==='
                // שלב שמשיך אוטומטית את הקוד לתוך ה-Workspace
                checkout scm
            }
        }

        stage('2. Compile Java Files') {
            steps {
                echo '=== מבצע קומפילציה לקבצי הג\'אווה ==='
                bat 'javac Dolev.java Hello.java'
            }
        }

        stage('3. Run Hello Application') {
            steps {
                echo '=== מריץ את קובץ Hello ==='
                bat 'java Hello'
            }
        }

        stage('4. Run Dolev Application') {
            steps {
                echo '=== מריץ את קובץ Dolev ==='
                bat 'java Dolev'
            }
        }
    }

    post {
        success {
            echo 'הפייפליין מ-Git קומפל והריץ את התוכניות בהצלחה!'
        }
        failure {
            echo 'הפייפליין נכשל. בדוק את הלוגים.'
        }
    }
}