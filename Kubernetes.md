---
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 25-07-22

---

# Kubernetes

## Kubernetes in few words

Everything in Kubernetes is a [[K8s - Resource]].

There are [[node]] which are [[K8S - Resource]]

### Node

### Namespace

We can create a namespace with a YAML (recommended) or with a CLI (not recommended) :
```shell
kubectl create ns bim
```

Create a namespace named `bim`.

YAML :
```yaml
kind: # type of resources
metadata:
	name: # name of resources
```

```
$ kubectl apply -f namespace.yaml # apply the namespace
```

### Pod

A pod is the smallest unit in k8s

### Deployment

An abstraction on top of pod
## Kubernetes in details

## References
