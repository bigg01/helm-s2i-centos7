oc new-project mytiller
export TILLER_NAMESPACE=mytiller

oc new-project $TILLER_NAMESPACE
oc process -f https://raw.githubusercontent.com/bigg01/helm-s2i-centos7/master/helm/tiller-template.yaml -p TILLER_NAMESPACE="${TILLER_NAMESPACE}" -p HELM_VERSION=v2.12.3 | oc create -f -


oc policy add-role-to-user edit "system:serviceaccount:${TILLER_NAMESPACE}:tiller"


