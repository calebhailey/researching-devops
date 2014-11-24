Product Summaries
===

**Description**: A review of the strengths, weaknesses and purpose of each of the tools surveyed in previous articles:

**Individual Reviews of**:

* [Chef-provisioner](./chef-metal.md)
* [Sparkleformation](./sparkleformation.md)
* [Terraform](./terraform.md)

## Observations

Each of these tools provide a varying array of features to configure, deploy, and maintain compute system stacks. Some are focused more around configuration while some are focused around dynamic or even run-time programmatic setup of templates. Providing a range from simple configuration to advanced programmatic complex management capabilities. Each of these tools works well for a range of scenarios with their own strengths and weaknesses.

## Getting Started

Each of these tools has a different learning curve. For each of these I've tested them by setting up an extremely simple AWS EC2 instance. With each instance I've created one other setting or custom configured resource. Each of these tools, in their respective getting started documentation, has exactly this.

The easiest to get started with was, by far Terraform. With each tool I started on a completely unprepared OS-X image. For Terraform the only prerequisties were Terraform itself. I didn't need to go configure Ruby, know anything about how a programming language is structured, or add additional tooling to get started with Terraform. This made ramping up with Terraform extremely easy to build out a simple instance and resource.

The second easiest was really a tie between Sparkleformation and Chef-provisioner. Both require various tools to fully use their feature sets. With Sparkleformation knife is needed and with Chef-provisioner various Chef tools are needed such as Chef-client and related prerequisites.

## Past Getting Started, Into the Fire