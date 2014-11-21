* Chef-metal
===
**[is now](https://twitter.com/jkeiser2/status/527601333709602816)** re: [https://twitter.com/jkeiser2/status/527601333709602816](https://twitter.com/jkeiser2/status/527601333709602816)
# [Chef-provisioning](https://github.com/opscode/chef-provisioning)

## What is Chef-Provisioning?

Chef Provisioning is a tool that provides a way to create and recreate systems environments. It has a plugin model that allows the introduction of various deployments to environments such as Digital Ocean, AWS, Vagrant, bare metal, and others.

The Chef-provisioning toolset is broken down into machine resource and drivers for abstraction purposes.

### Machine resource

The machine resource is familiar territory for someone who has previously used Chef. The machine resource is where recipes, tags and other things are declared, providing a topological description of the application recipes, machines and other elements that will run. These machine resources are described with a Ruby DSL syntax such as:

machine 'horizontaldestributedwebserver' do
	recipe 'nginx'
	tag 'riak_node'
end

min_num_webserver_nodes = 5

1.upto(min_num_webserver_nodes) do |i|
  machine 'riakian_node#{i}' do
		recipe 'distributeddb'
		tag 'riak_node'
	end
end

### Drivers

The drivers feature is what actually puts together the abstract definitions into running instances. The drivers acquire resources (cloud, containers or bare metal) and idempotently and then intelligently determine how to build the instances as defined. The drivers also handle connections to those machines and bootstrapping chef and cooking up the recipes.

## Installation

**Prerequisites**:

* Chef Client (For OS-X 10.9/10.10 install with `curl -L https://www.opscode.com/chef/install.sh | sudo bash`.
* [Chef Server](http://docs.getchef.com/server/) for installation instructions check out the [chef docs for installing the server](https://docs.getchef.com/install_server.html).

Getting Chef-provisioning is easy, based on all the prerequisites being installed, Ruby setup correctly, etc. Having all of those prerequisites setup is the most difficult of getting started with chef-provisioning.

In addition to the basic Chef setup that is needed, there are a number of other requirements assumed with the Chef setup such as the tugboat gem and other related tooling.

The next steps for installation of Chef-provisioning include:

1. gem install chef-provisioning chef-provisioning-vagrant
* export CHEF_DRIVER=fog:AWS
* chef-client -z simple.rb

The above is a sample setup for using Chef-provisioning against AWS. For more information on using the tool against other platforms like Vagrant or others, check out the github repo [README.md](https://github.com/opscode/chef-provisioning/blob/master/README.md).

A Final Feature Comment

When building TDD or BDD style code around operations, Chef-provisioning work with Test Kitchen, providing a way to test clusters and related deployments that are put together specifically for Chef-provisioning. This is a big advantage for this tool.

## Summary

Chef-provisioning sets up solid new precedents for deployments with Chef, in general. Even though the tool itself is simple at first, it actually requires existing Chef knowledge and experience to get an environment setup for Chef usage and also takes work to really get started using Chef-provisioner. This initial learning ramp up can be difficult when just getting started. But once everything is setup, it's an extremely powerful tool with open ended possibilities to build out complex infrastructure and the respective systems and applications deployed on that infrastructure.