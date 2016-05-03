# Denormalizer

## What is this?

This is a rigging which maintains a set of firebase subscriptions and mirrors
their contents in a delta source stream. Each user subscription carries a
selector which picks one or more database paths to write to (specifying an
encoder for each) and maintains a list of document deltas from the previous
cycle. The output can be recorded in a data structure of the user's choosing
using the source adapter.


## What is the intended use case?

In the application we are working on at NuMaya LLC, we have found numerous
problems with trying to mirror more complex datasets using more trivial nesting
structures and dictionaries. This module is intended to solve those problems
by providing a substantial backbone for 2-way data binding against firebase.


## Design

Special care is being taken to avoid introducing lots of new types. Documents,
for example, are raw JSON, which makes interoperation with FireBase pretty
seamless, interpretation of the data is left to the user.

In addition, the data storage is separated from the source, so that documents
can be organized in the manner best suited to the application while still
taking advantage of the transactional denormalized writes provided by
Denormalizer.


## Source, Sink, and Pipe

Source, Sink, and Pipe are dataflow helpers which provide a structured way of
handling streaming changes to data in your application in a data structure
agnostic way, so that you can use whatever datastructures best represent your
application's data.


## More

Denormalizer is a work in progress and is part of an application under
development by NuMaya LLC. Any other usage or feedback of this module would
be helpful and appreciated. Documentation and examples are planned.


## Acknowledgements

* [Robin Luiten](https://github.com/rluiten)
* [Thomas Weiser](https://github.com/ThomasWeiser)
