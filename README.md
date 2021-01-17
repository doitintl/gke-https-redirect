# gke-https-redirect
Demonstration how to use the newly introduced https redirect support in native GKE ingress resources (GCLB).

These files accompany my medium article [Finally: Redirect http to https in GKE ingress][1].

## Requirements

### GKE version

As mentioned in the article, your GKE cluster needs to be running at least a recent version 1.17-gke for this to work.

### Named IP adress

You will need a static reserved ip address going by the name of `gke-https-redirect`. Create it like this:

```
gcloud compute addresses create gke-https-redirect --global
```

### DNS Names

You will want to override the domain names listed in `managedcertificate.yaml`. Also make sure they exist and point to the IP adress you created above.

## Installation

```
kubectl apply -f k8s/
```

---

[1]: https://medium.com/@bernhard-weisshuhn/finally-redirect-http-to-https-in-gke-ingress-138d7420c1bc
