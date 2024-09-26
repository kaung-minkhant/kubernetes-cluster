## Metrics Server
Metrics server will be provisioned on controlplane via node affinity and tolerations. In order to make it work, we need to approve the certificates reqested by the nodes. Normally, `kubeadm init` uses self-signed certificates, which is not valid with metrics-server. Thus kubeadm is configured with serverTLSBootstrap.

After the cluster starts up, we need to approved the certificates.
1. list the pending certificates with ```k get csr```
2. approve the pending certificates with ```k certificate approve <certificate>```
