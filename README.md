# ssi-protocol

![ssi logo](ssi-logo.png)

This repo is a place to collaborate around interoperability of ecosystems
supporting self-sovereign identity. Anybody and everybody is welcome to
contribute docs that capture our thinking. Our goal is to find practical
common ground quickly, not to create heavy standards and processes. Nobody
owns content here except the contributors. (See [license note](#license-note) below.)

### Contributing

The rules for the repo are super simple: to contribute, raise a PR. A PR is
accepted as soon as it idles for 7 days without anyone making a substantive
counterproposal. At that point, the ideas in the PR are considered "tenatively
endorsed" by the contributors. New PRs can always undo something.

Everybody plays by these rules, including maintainers. And anybody can be a
maintainer, if you have good github kung fu and you'll enforce these rules.
We're all peers. 

For more details on contributing look [here](overview/how-to-contribute.md)

### Principles

As a community, we ask that everyone adheres to the 5 core principles:

  * [Doacracry](overview/core-principles.md#Doacracy)
  * [Privacy by Design](overview/core-principles.md#Privacy-by-Design)
  * [Interoperability](overview/core-principles.md#Interoperability)
  * [Extensible](overview/core-principles.md#Extensible)
  * [User-Centric](overview/core-principles.md#User-centric)
  * [Respectful]((overview/core-principles.md#Respectful)


### Structure

The repo is structured as follows:

* [`/overview`](overview/README.md) -- Background philosophy, motivation,
  references to standards that we want to use without regurgitating them
  here, etc.
* [`/pkg`](pkg/README.md) -- Docs on how to package communications between
  independent actors in an SSI ecosystem. Covers general conventions on
  encryption, serialization, etc -- things that are true regardless of the
  _content_ of communication. 
* [`/msg`](msg/README.md) -- Docs on different messages that might be exchanged.
  (Communication in SSI is assumed to be fundamentally message-based, though
  there are ways to adapt it to streaming, multicast, and similar use cases.)
  The `/msg` folder is further subdivided:
  * [`/msg/std`](msg/std/README.md) -- Standard messages of general interest,
  foundational to any SSI work. For example, an error message, messages to
  query and reply about the capabilities of another entity, messages about
  issuing credentials or proving things, or messages about how to route
  other messages. Messages are organized into __message families__ by subdir
  -- so there might be a subdir called `cred_issuance`, for example.
  * [`/msg/ext`](msg/ext/README.md) -- Message families of narrower interest, not
  necessary for general interop. For example, messages to control IoT sensors
  might go here. 
* [`/flow`](flow/README.md) -- Docs on different interaction patterns that
  matter in the ecosystem. Some of these patterns may relate to specific message
  families; others may apply to many different message types.
  * [`/flow/std`](flow/std/README.md) -- Standard interaction patterns of general
  interest, foundational to any SSI work. For example, the `negotiate` pattern
  or the `consent` pattern may apply broadly enough to qualify as a standard flow.
  * [`/flow/ext`](flow/ext/README.md) -- Flow families of narrower interest, such
  as the flow that occurs in a shopping cart checkout.
  
Files and folders, at least under `/msg` and `/flow`, are named with `snake_case`
so they can form the basis of a namespace hierarchy because we anticipate
implementing them in code, referencing them in test suites, etc.

##### Versions

We do not yet have a formal versioning strategy for the repo. Perhaps that will
change. In the meantime, if you want to reference something here with confidence
that it won't change, use a specific git hash.

##### License Note
Contributions to this repo become open source under an [Apache 2 license](LICENSE),
though you are welcome to copyright them yourself, too, if you like. We don't
expect the ideas here to embody secret sauce anyway, since they're all about
interop that we want the world to achieve, and we're writing docs rather than
code. See [this FAQ about Apache 2](
https://resources.whitesourcesoftware.com/blog-whitesource/top-10-apache-license-questions-answered
) for for specifics.
