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

Even though I didn't dive extensively into each tool just yet, I got a good feel for what each would be like for ongoing management of computing stacks.

I'll admit I lean a bit toward the programmatic side of things. With that in my favor it made it easy to determine what future management would be like with Sparkleformation. This gave Sparkleformation an easy edge over the other tooling since it is first and foremost a tool that can be used from a programmatic perspective.

The tool that rolled in second for ease of management over time was Chef-provisioner. This has a lot to do with the existing, and massive, capabilities of the Chef toolset in general. Chef-provisioner however starts off and pushes more of a configuration versus programmatic management of an environment. I tend to lean toward programmatic options over pure configuration options, especially in enterprise environments.

The most confusing tool ongoing was Terraform. The main reason was simply, once one works through the initial intro there isn't a quick or easy way to find things as examples. I'm sure this will change over time.

## Documentation & Finding Resources

Each of these tools has a user community, some bigger than others, but they're each present. People in the communities have spent time and effort to build well thought out and elegant tools. Terraform really stands out as a highly polished and super slick tool. Sparkleformation and Chef-provisioner both stand out in their structure and organization of configuration and code.

When diving into each of these tools, there was clearly an easier to use documentation set and a more difficult documentation set. The easiest to get started with, but increasingly difficult documentation set was Terraform. Sparkleformation was a little rough, but the documentation - being that this is a very beta tool - was well structured and read well with working examples.

Chef-provisioner left me with a short rant. Namely that naming a tool and then changing the name of the tool really wrecks havoc on finding resources via Google (or any search engine). During my review of the tool, Chef-provisioner had previously been referred to as Chef-metal. This changed and sent the documentation into a bit of chaos. I spent a lot of extra time digging through results, determining if documentation was deprecated or up to date, and if it applied to what I was actually trying to do or not. This left me frustrated more than a few times. However, in the end I was able to find what I need, but I'd highly suggest that the team putting together Chef put a little bit more effort into their docuemntation and how that shows up via search engines.

## Generalized Scenarios

It appeared after a short time working with each of these tools that each would work well in specific environments. Some for a lean startup with a minimal stack of varying providers, others with a complex mixed enterprise stack.

Terraform came off as a tool that would be great for a pretty lean stack that mixed and matched things. For instance a startup that had a range of web servers hosted at AWS, their network mixed between AWS and DNSimple, and then maybe some simple in house compute resources managed internally via Vagrant. However anything beyond that complexity would quickly become a little unqieldy without a thorough amount of pretty tricky documentation reading.

Chef-provisioner would be great for a really complex enterprise environment that mixes providers, prospectively has a Chef-server team and toolset already in place and wants to extend their management of systems in this way.

Sparkleformation, albeit simple in some ways and complex in others, is a great tool for companies that deal with lean or complex systems in virtualized providers like AWS. Over time this solution would prospectively be the simplest as it easily would integrate into build systems or other pre-existing environments. With the fact that it is a Ruby DSL, it immediately lends itself toward even self-managed and self-healing environments.

Any of these tools has great advantages. The first step in determining your usage is in analyzing and finding out your environmental needs. Once that is done it's just a matter of weighing the implementers priority, configuration vs. programmatic capabilities and moving forward. In the end, it may be one tool or multiple.