
# MongoDB Kubernetes stack

Run scripts in this order:

```
kubectl create -f mongo-secrets.yml
kubectl create -f mongo-pv.yml
kubectl create -f mongo-pvc.yml
kubectl create -f mongo-deployment.yml
```

## Secrets

Secrets must be stored with base64 encoding.

**encoding example**

```
echo "supercalifragilistico" | base64 
after encoding it, this becomes c3VwZXJjYWxpZnJhZ2lsaXN0aWNvCg==
```

**decoding example**

```
echo "c3VwZXJjYWxpZnJhZ2lsaXN0aWNvCg==" | base64 --decode
after decoding it, this will give supercalifragilistico
```


## Volume

To run this stack a volume is required a volume.
To run the stack locally, create a volume on Kind cluster called ``/persistent-volume``.