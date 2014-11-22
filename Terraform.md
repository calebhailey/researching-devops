# [Terraform]()

## What is Terraform?

Terraform is a tool created by Hashicorp that provides a common configuration for launching devops infrastructure to various sources. These sources can range to DNS providers like DNS Simple to cloud providers like AWS, Digital Ocean or directly to local sources via Vagrant. Unlike many tools for infrastructure management, Terraform is actually a standalone product that can be installed and used autonomously from any other infrastructure devops tooling.

The sample configuration that is shown on the Terraform.io site shows just how simple it is to setup and run a basic deploy with terraform.

		resource "aws_elb" "frontend" {
		    name = "frontend-load-balancer"
		    listener {
		        instance_port = 8000
		        instance_protocol = "http"
		        lb_port = 80
		        lb_protocol = "http"
		    }
		 
		    instances = ["${aws_instance.app.*.id}"]
		}
		 
		resource "aws_instance" "app" {
		    count = 5
		 
		    ami = "ami-043a5034"
		    instance_type = "m1.small"
		}

In the directory where this configuration is then simply running `terraform plan` which shows the execution plan and then `terraform apply`. That's it!

### Features and Functionalities

Terraform works around several key featuresets. There is the core that everything is based on, the configuration and commands (CLI). Then on top of that Terraform has: providers, provisioners, modules, and plugins.

Providers are basically the underlying elements of infrastructure that are deployed to. This includes services like AWS, CloudFlare, DigitalOcean, DNSimple, Heroku, and Others.

Provisioners are built around setting up a resource during it's initial creation. When an instance is launching this is the phase when additional applications or servers would prospectively be installed, copied and otherwise configured on the deployed instances.

Modules are configurations that are self-contained. They're managed in groups and can create reusable components in Terraform. This is a feature that opens up some abilities to build well formed code with reasonable organization. Usually modules are simply declared as shown.

		module "nameof" {
			source = "somepath.com/heavy/water/operations/aws"
			servers = 1000
		}

Plugins are somewhat self-descriptive for Terraform. However it is considered an extremely advanced topic that isn't required for daily operational use of the tools. To learn more about it jump into the docs at [plugin basics](https://www.terraform.io/docs/plugins/basics.html).

## Installation:

**Prerequisites**:

* Nothing.

Installing Terraform is an extremely simple process. The official intro [installation instructions are a quick read](http://www.terraform.io/intro/getting-started/install.html). The basic gist is:

1. [Download](http://www.terraform.io/downloads.html)
* Unzip the download to a path.
* [Set the PATH](http://stackoverflow.com/questions/14637979/how-to-permanently-set-path-on-linux).

## Summary

Overall Terraform is really simple. Sometimes the simplicity makes me question the tool, but so far Terraform has allayed my fears. As complexity increases Terraform does start to get a bit more cumbersome and other tools are usually needed to compensate for this. In really complex environments, which are prevalent in large enterprises, Terraform tends to be difficult to really use on a daily operational basis. For more information, check out the summary [post here](summarized.md).
