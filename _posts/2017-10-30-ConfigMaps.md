---
layout: post
title: 'Importance of Config Maps'
categories: devops
excerpt: 'environment-agnostic deployments hinge on this modularity'
---
As you move from development to production, you quickly see there's a lot more you need to configure with an application than just ports. Let's say you need to do things like performance tuning or hardening of the application. With orchestrated containers that can be a little challenging in an ephemeral environment. How do I test that my change works before I deploy it out to all my containers? Do I bake it into the Dockerfile? What happens when I need to make another change? Having an easy way to change an application's configuration is essential in a containerized environment.

In an orchestrated environment like Kubernetes, it's clear the resources that belong to which infrastructure category: compute (deployments, pods, etc), storage (persistent volumes) , network (ingress, services). These resources may stay static throughout the lifecycle of your application. However, configurations at the application level tend to be more dynamic. JVM heaps and Nginx configurations, for example, tend to vary per environment. 