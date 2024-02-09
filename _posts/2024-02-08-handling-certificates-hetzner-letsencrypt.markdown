---
layout: post
title:  "Create certificates at Kubernetes using Hetzner DNS"
date:   2024-02-08 8:33:12 +0100
categories: kubernetes certificates hetzner letsencrypt
---
Let's talk a bit about managing certificates automatically at our Kubernetes cluster.
In this example we'll use a Kubernetes cluster at MicroK8s, we'll use Hetzner DNS servers and Letsencrypt.

Currently there is not a lot running at this Kubernetes cluster yet, it's almost empty. I only installed `Traefik Proxy` on it and I want to expose the Traefik dashboard. Hence I need certificates because I only want secure traffic, even when it's on my own local network.

In order to automatically create/use certificates using `Letsencrypt` at your Kubernetes cluster, do:

1. Install cert-manager at your cluster
2. Install Hetzner webook in case you use Hetzner DNS API:<br>
<a href="https://github.com/mecodia/cert-manager-webhook-hetzner" target="_new">https://github.com/mecodia/cert-manager-webhook-hetzner</a>
3. sth