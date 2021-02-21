pipeline {

    agent any

    environment {
        SECRET_TEXT = credentials("my-secret-text-crendentials-id")
        USERNAME_PASSWORD = credentials("my-username-password-crendentials-id")
    }

    stages {
        stage("Don't tell secrets") {
            steps {
                echo "My secret text is ${env.SECRET_TEXT}" // My secret text is *****
                echo "My username is ${env.USERNAME_PASSWORD_USR}" // My username is ****
                echo "My password is ${env.USERNAME_PASSWORD_PSW}" // My password is ****
            }
        }
    }
}
