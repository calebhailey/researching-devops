Terraform, Chef-metal and Sparkleformation
===

[![Ready](https://badge.waffle.io/Adron/researching-devops.png?label=ready&title=Ready)](https://waffle.io/Adron/researching-devops)
[![In Progress](https://badge.waffle.io/Adron/researching-devops.png?label=In%20Progress&title=In%20Progress)](https://waffle.io/Adron/researching-devops)

[![Throughput Graph](http://graphs.waffle.io/Adron/researching-devops/throughput.svg)](https://waffle.io/Adron/researching-devops)

## Introduction
I've recently started looking into a number of tools to help automate projects from the development and operations point of views. As one might say these days, I was looking to *up my devops game*.

Over these last several months I've been building a lot of distributed systems. Primarily this work has focused solely around the AWS Ecosystem, with a few jaunts over to GCE or Azure spaces. While working through these projects I've run into a number of situations where automation is a primary indicator of a project being a success.

The easiest way, in most of these modern IaaS or even PaaS environments, is to get started with one of the available powerful tools for automation. In this series I'm going to take a look at a few of these automation tools and provide a basic intro to getting started with each. The three I'll take a look at are: [Terraform](https://www.terraform.io/), [Chef-metal/provisioning](https://github.com/opscode/chef-provisioning), and [Sparkleformation](https://github.com/sparkleformation/sparkle_formation).

## What is Terraform?

Terraform is a tool for building infrastructure in a way that it can be versioned, changed, and managed in an automatable way. It's a pretty easy installation and quick to get started with. I covered Terraform with a [how-to get started with appropriate document links and notes](./Terraform.md).

## What is Chef-metal?

First off, as of October 29th, in time for Halloween Chef-metal became [Chef-provisioning](https://twitter.com/jkeiser2/status/527601333709602816). Chef-metal, or as they're calling it [Chef-provisioning](https://github.com/opscode/chef-provisioning), is a way to manage various chef configured instances (via recipes) with a single source of code. This code can then be setup in a single repository. My [how-to on getting started I've provided here](./Chef-metal.md).

## What is Sparkleformation?

Sparkleformation is an early open source project by some of the team at one of the leading devops automation companies called [Heavy Water Ops](http://hw-ops.com/). I've written a simple [review of how-to get started with Sparkleformation](./sparkleformation.md).

## Additional Documents & Links

* [Documentarian Hacker Activist](./documentarian_hacker_activist.md)
* [Article Release Plan](./post-release-dates.md)
* [Other Notes](./othernotes.md)
* [Terraform, Chef-metal/provisioning, Sparkleformation Summary](./summarized.md)