```
# Odoo images

add new python modules in # Install python modules

add new odoo modules in dir modules

# build image 

sudo docker build -t odoo:xxx .
sudo docker tag odoo:xxx xxx/odoo:xxx
sudo docker push xxx/odoo:xxx

$CI_REGISTRY - Harbor address (example: https://harbor.example.com/)

$CI_HARBOR_ADDRESS_ODOO - Harbor project address (example: harbor.example.com/project_name/)

$CI_REGISTRY_PASSWORD - registry user password

$CI_REGISTRY_USER - registry username

$K8S_API_URL - k8s API address 

$K8S_CI_TOKEN - output of command : 

------------
kubectl get secret -n ci \
  $(kubectl get sa -n ci deploy \
    -o jsonpath='{.secrets[].name}') \
  -o jsonpath='{.data.token}'
-----------
 


```
```
Preparation for CI_TOKEN

$ kubectl create ns ci

$ kubectl create sa deploy -n ci

$ kubectl create rolebinding deploy \
  -n ci \
  --clusterrole edit \
  --serviceaccount ci:deploy


```

