node {
    stage('Example') {
        try {
            withDockerContainer('hashicorp/terraform:light').inside(--entrypoint=/bin/sh) {
			  sh 'terraform --version'
			}

        }
        catch (exc) {
            echo 'Something failed, I should sound the klaxons!'
        }
    }
}