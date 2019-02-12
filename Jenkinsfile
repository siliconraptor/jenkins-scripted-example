def labelBuild = "golang-${UUID.randomUUID().toString()}"
podTemplate(label: labelBuild, cloud: 'k8s-config', yaml: """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: terraform
    image: hashicorp/terraform:light
    tty: true
"""
) {
node {
    stage('Example') {
        try {
            withDockerContainer(args: '--entrypoint=""', image: 'hashicorp/terraform:light') {
			  sh 'terraform --version'
			}

        }
        catch (exc) {
            echo 'Something failed, I should sound the klaxons!'
        }
    }
}
}
