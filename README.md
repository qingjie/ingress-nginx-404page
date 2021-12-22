# ingress-nginx-404page
Ingress-nginx实现灰度金丝雀发布-Ingress-nginx自定义错误页面

* https://blog.51cto.com/heian99/3220054
* https://v2-1.docs.kubesphere.io/docs/zh-CN/quick-start/ingress-canary/
* https://blog.csdn.net/weixin_44692256/article/details/108581800
* https://github.com/kubesphere/tutorial

```
eksctl create cluster --name qzhao --region us-west-2

helm install ingress-nginx ingress-nginx/ingress-nginx -n ingress-nginx

kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.6.1/cert-manager.crds.yaml -n cert-manager
  helm install \
  cert-manager jetstack/cert-manager \
  --namespace cert-manager \
  --version v1.6.1 \
  --set prometheus.enabled=false \
  --set webhook.timeoutSeconds=4 
  
eksctl delete cluster --name qzhao --region us-west-2
```

* https://github.com/qingjie/cert-manager-letsencrypt-4
