# Flux for my k3pi cluster
### Intro
This repo has all of the manifests deployed in my Raspberry Pi K3s cluster.

### SOPS
To import the public key to make new secrets:
```gpg --import ./clusters/k3pi/sops.pub.asc```
To get the secret key to edit secrets (Need to import to gpg after receiving key):
```kubectl get secret -n flux-system sops-gpg -o jsonpath="{.data.sops\.asc}" | base64 -d```
Once you have both keys imported, you should be able to edit a sops files with
```sops <file_path>```