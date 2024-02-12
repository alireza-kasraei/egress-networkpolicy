Sample cluster which contains a reverse proxy nginx for "google" and network policy rules for restricting other pods except those which are labeled with the "ei" label, in the cluster to access google only through the nginx.

within this pod:
```
kubectl run --rm --restart=Never --image=alpine -i -t --labels="app=ei" test -- ash
```
google main page will be accessible by running ```wget nginx-service```

The same does not work for pods with "app" label other than ei.
