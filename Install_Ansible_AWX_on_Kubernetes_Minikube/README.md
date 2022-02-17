## Install AWX Operator
To install AWX operator, execute the following kubectl command
`kubectl apply -f https://raw.githubusercontent.com/ansible/awx-operator/0.12.0/deploy/awx-operator.yaml`

Check pods
`kubectl get pods`

## Create AWX Instance
Create yaml file
```yaml
---
apiVersion: awx.ansible.com/v1beta1
kind: AWX
metadata:
  name: ansible-awx
spec:
  service_type: nodeport
  ingress_type: none
  hostname: ansible-awx.example.com
```

## Deploy Ansible AWX Instance
`kubectl apply -f ansible-awx.yml`

## Monitor Logs (if needed)
`kubectl logs -f deployment/awx-operator`


