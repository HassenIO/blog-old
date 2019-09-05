---
title: Gentle Introduction to Terraform
date: "2019-09-01T00:00:00.000Z"
description: Here I talk about my love for Terraform, a tool to create and manage your cloud infrastructure resources.
---

Hello World,

You may probably heard about [Terraform (by Hashicorp)](https://www.terraform.io/), a tool to create and manage your cloud infrastructure resources. If you don't know what it is doing, or very few, but want to know more about it, so keep reading. I'll try in this post to give you enough knowledge and resources to make you dig deeped and make Terraform a part of your favourite tools, like I did.

So here we go.

## tl;dr

Terraform is an open source tool that helps you define and create your infrastructure resources (like AWS EC2 instances, S3 buckets, VPCs, ...etc) in a IaC way (Infrastructure as Code): You list and configure your resources in `.tf` files, and let Terraform provision, update or delete that resources, and everything needed to use them. It has a neat learning curve so you can be productive very quickly.

## What exactly is Terraform?

Suppose you have you application ready to be deployed on AWS. And let's also suppose you don't have the option to say: "This is not my problem, we have an Ops to handle that."

> I will only talk about AWS resources in this post, but Terraform can work with many other cloud providers, like Google Cloud, Digital Ocean, Azure, AliCloud,... etc. [Here is a list of supported providers](https://www.terraform.io/docs/providers/type/major-index.html).

You have many ways to do that:

### Option 1: AWS Console

You open the AWS console, and create your infrastructure one resource at a time. We all did that at some point.

All works fine, but now you need to replicate this for all of your environments. You also have to manually copy/paste resource names, ARNs, allocated IP addresses,... etc. Let alone you need new resources, drop other resources, handle with other developers requests,... etc.

Let's face it, it quickly becomes quirky and not fun. And then you hear about CloudFormation...

### Option 2: AWS CloudFormation

With CloudFormation, you define what your infrastructure needs in a JSON or YAML file. All resources are listed there, with all specs necessary to fill you needs. You now commit this file and all developers in your teem can access that file, and collaborate around the infrastructure. Replicability is now a problem of the part.

You now know the poser of IaC (Infrastructure as Code). It's a game changer, and now you'll never go back (do you?).

But there are still gotchas...

- **It's very verbose**. Yes, you have YAML to reduce line numbers, but it's still a 1000 lines file (at average for a production grade app). It takes some times to know how all things get interconnected, which leads to...
- **It's intimidating for new developers**. If you worked on a project that has a CloudFormation file in it, you know what I mean! It's a new syntax and the learning curve seems very steep at the beginning.
- **It's a lot of copy/paste**. I don't know how you are accustomed to work with CloudFormation, but in my case it starts with googling, then going to an AWS CloudFormation doc page, then copy/paste the JSON/YAML snippet to my project and customizing some attributes (like resource names or specs).
- **It's not portable**. If you only want to work with AWS, that's not a big deal. But going to another cloud provider will require a complete rewrite of your IaC.

In the defense of AWS, CloudFormation is really powerful and allows you to codify whatever service you want from AWS. Most of other cloud providers have equivalents of CloudFormation, but they also share the gotchas.

### Option 3: Third party IaC tool

Terraform is one solution among others (most notably Ansible). It is a multi-cloud IaC tool, which means it allows you to define your infrastructure for many cloud providers using a single syntax. Going from one provider to another does require some adjustments, but not a complete rewrite. You can even mix providers, that's not a problem.

It uses a more flexible and easy to read syntax, in that it's not a static JSON file. The Terraform syntax allows you to use variables and data stores to handle different environments. 

## Why should I use it?

--Todo give some usecases

## An example

--Todo give a use case to deploy a web app

With Terraform, we provision an EC2 instance to add nginx server.

## Where to go from now?

--Todo give resources on whet to do next to learn more
--Todo explain other alternatives (Puppet, Chef, Ansible,...) and how they work with Terraform

## Take away