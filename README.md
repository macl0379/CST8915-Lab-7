# CST8915-Lab-7

**Student Name**: Collin MacLeod
**Student ID**: macl0379
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Fall 2026

---

## Introduction 

In this lab, you will explore the foundational concepts of Kubernetes, focusing on using kubectl for basic operations, understanding the structure of Kubernetes YAML configuration files, and creating essential Kubernetes resources such as Pods, Deployments, and Services.

### Learning Goals

- Understand the basic structure of a Kubernetes YAML file.
- Learn how to create Kubernetes objects using kubectl and YAML files.

---

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/6VuIIO1xaE4)

---

## RabbitMQ Configurations & Issues

Rabbit MQ is stateful because it manages and stores the messages it collects, the routing rules and metadata on a disk. If no persistent storage is in place, this data will be stored inbside the environment in ephemeral storage. This makes it sensitive to the node being deleted or restarted as all data and routing behaviour will be lost with the node if there is no replication in place.

One method to solve this is deploying the RabbitMQ node with a StatefulSet. This setting enables the nodes to maintain a sticky identity and ensures that pods are ordered correctly and are all unique. While this doesn't mean the RabbitMQ node isn't susceptible to failure, it does allow for persistent storage which would mean deleting or restarting the node will not lose the queue data or the routing rules.

Azure Service Bus would also solve the problem by completely replacing RabbitMQ. When using Azure Service Bus the data and metadata are automatically persistent across Azure storage provided through the PaaS offering.