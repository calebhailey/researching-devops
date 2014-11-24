# [Sparkleformation](https://github.com/sparkleformation/sparkle_formation)

## What is Sparkleformation?

[Sparkleformation](https://github.com/sparkleformation/sparkle_formation) is a Ruby based DSL specifically focused around describing and, combined with chef & knife, can be used to deploy infrastructre resources in AWS and Rackspace with other cloud environments being added in the future.

The best way to get an idea of the DSL and dive into the functionality is to take a look at the initial template that is shown in the [docs READM.md](https://github.com/sparkleformation/sparkle_formation/tree/master/docs#what-it-looks-like).

### Sparkleformation Building Block

In this basic starter template from the README.md we can see several of the key features of the Sparkleformation DSL. First there are the three key building blocks: Components, Dynamics, and Registries.

**Components** are the core part of Sparkleformation that provides static configuration for reuse between multiple stack templates.

**Dynamics** are a way to create unique resources via parameter passing. This allows for changing parts of a template at run time, adding capabilities to the code reuse and varying nature of environments.

**Registries** are used to define reusable properties between resources of different types.

### Other Features

**Template Anatomy** is a featureset broken into; parameters, resources, mappings, and outputs. Each of these feature elements provide code metadata and variable features for writing the various template elements.

**Intrinsic functions** are AWS Cloudformation specific functions. They're not implemented for all providers yet. For more information on intrinsic functions check out [specifying intrinsic functions](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-fuctions-structure.html) and the [intrinsic function reference](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference.html). This featureset of Cloudformation provides a way to conditionally create stack resources. The conditinos of the functions are evaluated based on parameters declared when creating the stack.

**Universal Properties** are a feature that currently exists of tags that can be applied to many resources. This helps in determining which resources is which within the stack. The tags are setup in a standard key value pair set within an array fo the key value pairs.

## Installation:

**Prerequisites**:

* [Ruby 1.9.3](https://www.ruby-lang.org/en/downloads/) or newer. The current version is [2.1.5](https://www.ruby-lang.org/en/downloads/).
* [knife](https://docs.getchef.com/knife.html) 

Installation is a little tricky since the product is still in a beta state, albeit things may be changing real soon with new knife releases. It's solid, there are just a few extra configuration and steps to tweak things before getting up and running smoothly. For a quick walk-through of the installation steps check out the docs [Getting Started](https://github.com/sparkleformation/sparkle_formation/tree/master/docs#getting-started) section.

## Summary

Sparkleformation provides a Ruby based DSL that creates a readable and more dynamic system in which to manage CloudFormation Templates, and prospectively whatever template systems are added in the future. With a DSL like Sparkleformation one has very powerful ability to programmatically manage computing resources in the AWS (or Rackspace) stack.