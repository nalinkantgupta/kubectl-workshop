# Level Up - troubleshooting

## Access the Container

```yaml
# Dummy Shell container for troubleshooting
k run --rm -it container-tbd --image=alpine --restart=Never -- sh

# DNS Query from Another Container
k run --rm -it --image=alpine dns-query-tbd -- sh \
  -c 'test=`wget -qO- -T 2  http://google.com 2>&1` && echo "$test OK ✅" || echo "Failed ❌"'

# Port checking
k run --rm -it --image=alpine port-query-tbd -- sh \
 nc -vz -w 2  10.44.0.1  3306

# AWS IAM Permission Issue Checker
k get sa
k run --rm -it serviceaccount-permission-tbd \
      --image amazon/aws-cli \
      --serviceaccount Mention-Yourservice-Account \
      --restart Never \
      -- s3 ls


# List Image Pods
k get pods web-deploy-85db94bcb5-qfmm5 -o jsonpath='{.spec.containers[*].image}'

# Resources limit Deployment
k get deployment web-deploy-secret -o jsonpath='{.spec.template.spec.containers[*].resources}'

# Env limit Deployment
k get deployment web-deploy-secret -o jsonpath='{.spec.template.spec.containers[*].env}' | jq

# List of Ports
k get deployment web-deploy-secret -o jsonpath='{.spec.template.spec.containers[*].ports}' | jq

# Deloyment events
k get deployment web-deploy-secret -o jsonpath='{.status.conditions}' | jq

# Get Secret Value
k get secret my-secret-env -o jsonpath='{.data}'
k get secret my-secret-env -o jsonpath='{.data.username}' | base64 --decode
```
