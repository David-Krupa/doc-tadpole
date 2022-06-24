<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

## Tools: Best of

This document was created from Sam’s mentions of interesting tools from May 2018 through May 2020 on the #nerd-devops, #nerd-codeparty, and #nerd-insecurity channels.

You can safely assume it needs to be updated.

### Ansible

*   Auto-generating docs: [https://ansible-readme.readthedocs.io/en/latest/](https://slack-redir.net/link?url=https%3A%2F%2Fansible-readme.readthedocs.io%2Fen%2Flatest%2F)

  While this tool is/was pretty good, it's been archived and is unmaintained. Unfortunately i couldn't find a good alternative.
 [https://github.com/ansible/proposals/issues/19](https://github.com/ansible/proposals/issues/19)

### Atom

*   [Guides and API reference](https://atom.io/docs)
*   [Atom forum](https://discuss.atom.io/)
*   [Atom.org](https://github.com/atom), where all GitHub-created Atom packages live.
*   Packages:
    *   [https://atom.io/packages/atom-beautify](https://atom.io/packages/atom-beautify)
    *   [https://atom.io/packages/ide-json](https://atom.io/packages/ide-json)
    *   [https://atom.io/packages/language-groovy](https://atom.io/packages/language-groovy)


### AWS



*   [Instance Identity Documents - Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-identity-documents.html): Use an instance identity document to verify the attributes of your instance.


### Cloud/Cloud Native



*   [https://landscape.cncf.io/](https://landscape.cncf.io/)


### Documenting code

[https://adr.github.io/madr/](https://adr.github.io/madr/)

(More on this in another doc)


### Containers


  I wouldn't expect someone to know these standards verbatim, but they should know they exist and is what modern images and runtimes are aiming towards.

*   [https://www.opencontainers.org/faq](https://www.opencontainers.org/faq)
*   [https://github.com/opencontainers/runtime-spec](https://github.com/opencontainers/runtime-spec)
*   [https://github.com/opencontainers/image-spec](https://github.com/opencontainers/image-spec)


  There are runtimes other than Docker

*   [https://kubernetes.io/docs/setup/production-environment/container-runtimes/](https://kubernetes.io/docs/setup/production-environment/container-runtimes/)

Best practices

*   [https://docs.docker.com/develop/develop-images/dockerfile_best-practices/](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)

Security

*   [https://docs.docker.com/engine/security/](https://docs.docker.com/engine/security/)
*   [https://www.stackrox.com/post/2019/09/docker-security-101/](https://www.stackrox.com/post/2019/09/docker-security-101/)
*   [https://sysdig.com/blog/7-docker-security-vulnerabilities/](https://sysdig.com/blog/7-docker-security-vulnerabilities/)

Generate SELinux policies for containers.

*   [udica](https://github.com/containers/udica#udica---generate-selinux-policies-for-containers)
*   Using SELinux with container runtimes. [https://www.youtube.com/watch?v=FOny29a31ls](https://www.youtube.com/watch?v=FOny29a31ls)


### Docker/Dockerfile

*   [https://github.com/replicatedhq/dockerfilelint](https://github.com/replicatedhq/dockerfilelint)
*   [https://github.com/hadolint/hadolint](https://github.com/hadolint/hadolint)


### Elastic

*   [https://opendistro.github.io/for-elasticsearch/](https://opendistro.github.io/for-elasticsearch/)


### Kubernetes

*   [https://github.com/argoproj/argo-cd/blob/master/README.md#community-blogs-and-presentations](https://github.com/argoproj/argo-cd/blob/master/README.md#community-blogs-and-presentations)
    *   Deploying and updating K8s manifests, typically triggered by actions performed against the git-repo (commits, merges, releases, tags).  Allows for easy roll back if deployments fail.
    *   I think I've heard that Camp/Platform1 might be using [argo-cd](https://argoproj.github.io/argo-cd/) for things specifically for the IATT environment
    *   They’re also [running Argo CD](https://argocd.spacecamp.ninja/applications/test-ccat-chatup?view=network) via the pipeline at the deploy test stage
*   you can sort of lint kustomize overlays using kustomize piped to kube eval:

    ```
    kustomize build apps/ebs/base | kubeval --strict
PASS - stdin contains a valid StorageClass (ebs)
kustomize build apps/ebs/dev | kubeval --strict
WARN - stdin contains an invalid StorageClass (ebs) - parameters: Invalid type. Expected: [string,null], given: boolean
    ```

*   Kubernetes Network Policy Recipes: [https://github.com/ahmetb/kubernetes-network-policy-recipes](https://github.com/ahmetb/kubernetes-network-policy-recipes)
*   [kube-bench](https://github.com/aquasecurity/kube-bench) is a Go application that checks whether Kubernetes is deployed securely by running the checks documented in the [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes/).
*   [kURL](https://github.com/replicatedhq/kurl/). Production-grade, airgapped Kubernetes installer combining upstream k8s with overlays and popular components
    *   kURL - [Supported Kubernetes add-ons](https://kurl.sh/add-ons)
*   [Kubernetes Volumes 2:  Understanding Persistent Volume (PV) and Persistent Volume Claim (PVC)](https://youtu.be/OulmwTYTauI)
*   [https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/)
*   [Kubernetes Volumes 2:  Understanding Persistent Volume (PV) and Persistent Volume Claim (PVC)](https://youtu.be/OulmwTYTauI)
*   [https://www.magalix.com/blog](https://www.magalix.com/blog) \
It details common patterns in Kubernetes which helps beginners understand how things are done


### Linters

*   [https://github.com/hadolint/hadolint](https://github.com/hadolint/hadolint)


### SELinux

*   [udica](https://github.com/containers/udica#udica---generate-selinux-policies-for-containers). Generate SELinux policies for containers.
*   Using SELinux with container runtimes. [https://www.youtube.com/watch?v=FOny29a31ls](https://www.youtube.com/watch?v=FOny29a31ls)


### Machine Images

*   [https://www.packer.io/](https://www.packer.io/intro/)


### News Sources

*   [https://aws.amazon.com/blogs/aws/](https://aws.amazon.com/blogs/aws/)
*   [https://confluence.atlassian.com/bitbucketserver/bitbucket-server-security-advisories-776640597.html](https://confluence.atlassian.com/bitbucketserver/bitbucket-server-security-advisories-776640597.html)
*   [https://www.openssl.org/news/](https://www.openssl.org/news/)
*   [https://help.github.com/articles/choosing-the-delivery-method-for-your-notifications/#choosing-the-delivery-method-for-security-alerts-for-vulnerable-dependencies](https://help.github.com/articles/choosing-the-delivery-method-for-your-notifications/#choosing-the-delivery-method-for-security-alerts-for-vulnerable-dependencies)
    *   [https://blog.github.com/2017-11-16-introducing-security-alerts-on-github/](https://blog.github.com/2017-11-16-introducing-security-alerts-on-github/)
*   [https://help.quora.com/hc/en-us/articles/360020212652](https://help.quora.com/hc/en-us/articles/360020212652)
*   [https://www.bleepingcomputer.com/news/security/](https://www.bleepingcomputer.com/news/security/)
*   [https://github.com/devsecops/awesome-devsecops](https://github.com/devsecops/awesome-devsecops)


### Service Mesh/Microservices

*   Istio [https://istio.io/](https://istio.io/)
*   [https://linkerd.io/](https://linkerd.io/)
*   [Kuma](https://github.com/Kong/kuma) is a platform agnostic open-source control plane for Service Mesh and Microservices. It can run and be operated natively across both Kubernetes and VM environments, making it easy to adopt by every team in the organization. I haven't used Kuma, but it could be interesting to bring modern security mesh practices to more traditional VM based workloads.


### Vagrant/virtualbox

*   I started using molecule and vagrant for testing ansible things on my OS X workstation and was annoyed with the audio issues it caused so pro tip:

 ```
config.vm.provider "virtualbox" do |vb|
   vb.customize ["modifyvm", :id, "--audio", "none"]
 end
 ```

 and for molecule

  ```
platforms:
  - name: instance
    box: centos/7
    provider_raw_config_args:
      - "customize ['modifyvm', :id, '--audio', 'none']"
```


#### DX? Maybe

[https://www.kennethlange.com/4-must-read-articles-on-developer-experience-dx/](https://www.kennethlange.com/4-must-read-articles-on-developer-experience-dx/)
