# Other Notes

## General Global Project Notes

1. After digging through installation described @ the beginning of the latest docs [README.md](https://github.com/sparkleformation/sparkle_formation/blob/master/docs/README.md) one priority I'd advance is to provide a cleaned up installation experience. Needing to custom configure the Gemfile and Knife Config is kind of a bit narly to do as a first step, some type of default config should be available to give anyone trying out sparkleformation an easy route to their first *"hello world!"* experience.
* ...

## Notes Specific to Docs

The topics based on docs, with links to the docs.

- [Building Blocks](building-blocks.md)
  - [Components](building-blocks.md#components)
  - [Dynamics](building-blocks.md#dynamics) See comment #1 below.
  - [Registries](building-blocks.md#registries) See comment #1 below.
- [Template Anatomy](anatomy.md)
  - [Parameters](anatomy.md#parameters)
  - [Resources](anatomy.md#resources)
  - [Mappings](anatomy.md#mappings)
  - [Outputs](anatomy.md#outputs)
- [Intrinsic Functions](functions.md)
  - [Ref](functions.md#ref)
  - [Attr](functions.md#attr)
  - [Join](functions.md#join)
- [Universal Properties](properties.md)
 - [Tags](properties.md#tags)
<hr/>
1. It might be a good idea from an IA (Information Architecture) point of view to put Dynamics and Registries into a single defined topic space. So Components are then the "static" space and "dynamic" elements are in a different space.
* ...