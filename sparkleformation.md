# [Sparkleformation](https://github.com/sparkleformation/sparkle_formation)

## What is Sparkleformation?

[Sparkleformation](https://github.com/sparkleformation/sparkle_formation) is a Ruby based DSL specifically focused around describing and, combined with chef & knife, can be used to deploy infrastructre resources in AWS and Rackspace with other cloud environments being added in the future.

The best way to get an idea of the DSL and dive into the functionality is to take a look at the initial template that is shown in the [docs READM.md](https://github.com/sparkleformation/sparkle_formation/tree/master/docs#what-it-looks-like).

		SparkleFormation.new('website') do

		  set!('AWSTemplateFormatVersion', '2010-09-09')

		  description 'Supercool Website'

		  resources.cfn_user do
		    type 'AWS::IAM::User'
		    properties.path '/'
		    properties.policies _array(
		      -> {
		        policy_name 'cfn_access'
		        policy_document.statement _array(
		          -> {
		            effect 'Allow'
		            action 'cloudformation:DescribeStackResource'
		            resource '*'
		          }
		        )
		      }
		    )
		  end

		  resources.cfn_keys do
		    type 'AWS::IAM::AccessKey'
		    properties.user_name ref!(:cfn_user)
		  end

		  parameters.web_nodes do
		    type 'Number'
		    description 'Number of web nodes for ASG.'
		    default 2
		  end

		  resources.website_autoscale do
		    type 'AWS::AutoScaling::AutoScalingGroup'
		    properties do
		      availability_zones({'Fn::GetAZs' => ''})
		      launch_configuration_name ref!(:website_launch_config)
		      min_size ref!(:web_nodes)
		      max_size ref!(:web_nodes)
		    end
		  end

		  resources.website_launch_config do
		    type 'AWS::AutoScaling::LaunchConfiguration'
		    properties do
		      image_id 'ami-123456'
		      instance_type 'm3.medium'
		    end
		  end

		  resources.website_elb do
		    type 'AWS::ElasticLoadBalancing::LoadBalancer'
		    properties do
		      availability_zones._set('Fn::GetAZs', '')
		      listeners _array(
		        -> {
		          load_balancer_port '80'
		          protocol 'HTTP'
		          instance_port '80'
		          instance_protocol 'HTTP'
		        }
		      )
		      health_check do
		        target 'HTTP:80/'
		        healthy_threshold '3'
		        unhealthy_threshold '3'
		        interval '5'
		        timeout '15'
		      end
		    end
		  end
		end

## Installation:

**Prerequisites**:

* [Ruby 1.9.3](https://www.ruby-lang.org/en/downloads/) or newer. The current version is [2.1.5](https://www.ruby-lang.org/en/downloads/).
* [knife](https://docs.getchef.com/knife.html) 

Installation is a little tricky since the product is still in a beta state, albeit things may be changing real soon with new knife releases. It's solid, there are just a few extra configuration and steps to tweak things before getting up and running smoothly. For a quick walk-through of the installation steps check out the docs [Getting Started](https://github.com/sparkleformation/sparkle_formation/tree/master/docs#getting-started) section.





## Summary