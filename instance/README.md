# Ansible Automation Platform instances

## Installs the Automation Controller
```
oc apply -k aap-openshift/operator/overlays/stable-2.1
```

## Prerequisites
Generate and Download the manifest manifest_ansible-tower.zip from https://access.redhat.com/management

How to generate it: https://www.redhat.com/en/blog/how-create-and-use-red-hat-satellite-manifest

### Create the secret named manifest using the following command.
```
oc create secret generic manifest -n ansible-automation-platform --from-file=manifest=manifest_ansible-tower.zip 
```

## Installs the Automation Controller Instance
```
oc apply -k aap-openshift/instance/overlays/default
```