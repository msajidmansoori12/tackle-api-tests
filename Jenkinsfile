pipeline {
    agent {
        label 'minikube-fedora35'
    }

    stages {
        stage('Hello') {
            steps {
                checkout scm
                echo "hello from new branch"
            }
        }
        stage('Test REGEX'){
            when{
                branch pattern: '^PR-.*$',
                comparator: 'REGEXP'
            }
            steps{
                echo "Branch is a PR" 
            }
        }
//         stage('Install minikube'){
//             steps{
//                 script{
//                     sh """ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
//                             chmod +x minikube
//                             minikube_homedir=/usr/local/bin/
                            
//                             sudo install minikube /usr/local/bin


//                             minikube start --driver=podman --memory=4g
//                             minikube addons enable dashboard
//                             minikube addons enable ingress
//                             minikube addons enable olm
//                             kubectl apply -f https://raw.githubusercontent.com/operator-framework/operator-lifecycle-manager/master/deploy/upstream/quickstart/crds.yaml
//                             kubectl apply -f https://raw.githubusercontent.com/operator-framework/operator-lifecycle-manager/master/deploy/upstream/quickstart/olm.yaml

//                             kubectl apply -f https://raw.githubusercontent.com/konveyor/tackle2-operator/main/tackle-k8s.yaml

//                             while [ \$(kubectl get crd|grep tackle|wc -l) != 2 ]
//                             do echo "Waiting for Tackle CRDs..."
//                             sleep 5s
//                             done

//                             """
//                     sh '''cat <<EOF | oc apply -f -
// kind: Tackle
// apiVersion: tackle.konveyor.io/v1alpha1
// metadata:
//   name: tackle
//   namespace: konveyor-tackle
// spec: {
//   keycloak_sso_req_passwd_update: "false",
//   hub_bucket_volume_size: 20Gi,
//   maven_data_volume_size: 20Gi  
// }
// EOF

// '''
// sh ''' sleep 2000s '''
//                 }
//             }
//         }
    }
}
