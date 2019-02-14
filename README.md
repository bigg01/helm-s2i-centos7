docker build -t bigg01/helm-s2i-centos .

export TILLER_NAMESPACE=tiller

oc process -f https://github.com/openshift/origin/raw/master/examples/helm/tiller-template.yaml -p TILLER_NAMESPACE="${TILLER_NAMESPACE}" -p HELM_VERSION=v2.12.3 | oc create -f -


oc policy add-role-to-user edit "system:serviceaccount:${TILLER_NAMESPACE}:tiller"