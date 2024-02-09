---
layout: post
title:  "Install Hetzner webhook"
date:   2024-02-08 7:03:52 +0100
categories: kubernetes certificates letsencrypt hetzner
---
Install Hetzner webook in case you use Hetzner DNS API:<br>
<a href="https://github.com/mecodia/cert-manager-webhook-hetzner" target="_new">https://github.com/mecodia/cert-manager-webhook-hetzner</a>

in short:

{% highlight bash %}
git clone https://github.com/mecodia/cert-manager-webhook-hetzner.git
cd cert-manager-webhook-hetzner/
helm install --namespace kube-system cert-manager-webhook-hetzner ./charts/cert-manager-webhook-hetzner
{% endhighlight %} 

output

{% highlight bash %}
chris@kube-2:~/projects$ git clone https://github.com/mecodia/cert-manager-webhook-hetzner.git
Cloning into 'cert-manager-webhook-hetzner'...
remote: Enumerating objects: 435, done.
remote: Counting objects: 100% (28/28), done.
remote: Compressing objects: 100% (23/23), done.
remote: Total 435 (delta 8), reused 19 (delta 5), pack-reused 407
Receiving objects: 100% (435/435), 213.72 KiB | 1.87 MiB/s, done.
Resolving deltas: 100% (199/199), done.
chris@kube-2:~/projects$ cd cert-manager-webhook-hetzner/
chris@kube-2:~/projects/cert-manager-webhook-hetzner$ helm install --namespace kube-system cert-manager-webhook-hetzner ./charts/cert-manager-webhook-hetzner
NAME: cert-manager-webhook-hetzner
LAST DEPLOYED: Fri Feb  9 13:22:59 2024
NAMESPACE: kube-system
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
It's running!
chris@kube-2:~/projects/cert-manager-webhook-hetzner$

{% endhighlight %} 

You'll see an additional namespace and some pods

[![cert-manager k9s](/images/cert-manager-k9s.png)](/images/cert-manager-k9s.png)