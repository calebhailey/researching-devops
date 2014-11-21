# [Terraform]()

## What is Terraform?

Terraform is a tool created by Hashicorp that provides a common configuration for launching devops infrastructure to various sources. These sources can range to DNS providers like DNS Simple to cloud providers like AWS, Digital Ocean or directly to local sources via Vagrant. Unlike many tools for infrastructure management, Terraform is actually a standalone product that can be installed and used autonomously from any other infrastructure devops tooling.

## Installation:

**Prerequisites**:

* Nothing.


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

