#Minishift

## Tag image with a new tag
`oc tag <project>/<build>:<label> <project>/<build>:<label>`

## Remove scc
oc adm policy remove-scc-from-user anyuid -z jenkins

## Start a failing container
oc debug dc/<BUILD_NAME>

## SSh into a container
oc rsh <CONTAINER_NAME>

## SET ENV Variable
oc set env dc/<CONTAINER_NAME> <VARIABLE_NAME>=<VARIABLE_VALUE>

## List env variables
oc set env dc/helloworld --list

## Get Logs
oc logs <CONTAINER_NAME>

### Get logs from terminated container
oc logs <CONTAINER_NAME> --previous

## List pods
oc get pods --selector <LABEL>=<VALUE>

## Describe pod
oc describe pod/<NAME>

## Create a project
oc new-project <Short Name> --display-name="<NAME>"

## Add template
oc create -f <TEMPLATE_URL>

## Create an app from a template
oc new-app <TEMPLATE_NAME> --name="<APP NAME>"

## List tempaltes
oc get templates

## List templates in namespace
oc get templates -n <NAMESPACE>

## Describe help
oc describe

## Edit files as json
oc edit dc/<POD_NAME> -o json

## Delete project
oc delete project <PROJECT_NAME>

## Delete all with a selector
oc delete all --selector <LABEL_NAME>=<LABEL_VALUE>

## Create a service with a selector
oc create service nodeport <SELECTOR> --tcp=5000:5000

## Create an insecure route for a service
oc expose service nginx

## Create secure route for a service
oc create route <TERMINATION> --service=<SELECTOR>
edge        Create a route that uses edge TLS termination
passthrough Create a route that uses passthrough TLS termination
reencrypt   Create a route that uses reencrypt TLS termination

