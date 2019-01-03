node {
    stage('Example') {
        try {
            withDockerContainer('hashicorp/terraform:light') {
			  sh 'terraform --version'
			}

        }
        catch (exc) {
            echo 'Something failed, I should sound the klaxons!'
        }
    }
}