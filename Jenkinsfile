node {
    stage('Example') {
        try {
            withDockerContainer(args: '--entrypoint=/bin/sh', image: 'hashicorp/terraform:light') {
			  sh 'terraform --version'
			}

        }
        catch (exc) {
            echo 'Something failed, I should sound the klaxons!'
        }
    }
}