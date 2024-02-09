---
layout: post
title:  "Create a basic Kubernetes playground"
date:   2024-02-07 10:46:42 +0100
categories: kubernetes basics
---
This article assumes you have an operational instance of <a href="https://microk8s.io/" target="_new">MicroK8s</a> installed somewhere at some server.
You can also install it locally of course, it all depends how you personally like to work.

I installed an Ubuntu server on a virtual machine at my network and selected to install MicroK8s during the installation of my server.
Once installed, it requires your user to be a member of the microk8s group. This info can be found at <a href="https://microk8s.io/docs/getting-started" target="_new">https://microk8s.io/docs/getting-started</a>

{% highlight bash %}
sudo usermod -a -G microk8s $USER
sudo chown -f -R $USER ~/.kube
su - $USER
{% endhighlight %}

now run

{% highlight bash %}
microk8s status
{% endhighlight %}

and you'll get something like this

[![microk8s status](/images/microk8s-status.png)](/images/microk8s-status.png)

You’ll see currently only 4 addons are enabled by default. When you really start using this playground, you'll notice need more. In the screenshot below you can see the status of my other server which I'm using for quite some time and which has all addons enabled I currently need.

[![microk8s status](/images/microk8s-status-addons.png)](/images/microk8s-status-addons.png)

To enable them, type:

{% highlight bash %}
microk8s enable cert-manager
microk8s enable dashboard
microk8s enable hostpath-storage
microk8s enable ingress
microk8s enable metallb
microk8s enable metrics-server
microk8s enable rbac
microk8s enable storage
{% endhighlight %}  

You now have a working, useable Kubernetes environment to play arround.