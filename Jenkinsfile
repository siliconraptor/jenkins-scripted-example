import java.util.UUID

def labelBuild = "test-${UUID.randomUUID().toString()}"
podTemplate(label: labelBuild, cloud: 'k8s-config', yaml: """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: golang
    image: 981303859063.dkr.ecr.us-west-2.amazonaws.com/golang:1.11.5-dep
    tty: true
"""
)

{
	node(labelBuild) {
	    stage('Example') {
	        try {
	            container('golang') {
				  sh 'ls -lart'
				}
	
	        }
	        catch (exc) {
	            echo 'Something failed, I should sound the klaxons!'
	        }
	    }
	}
}
