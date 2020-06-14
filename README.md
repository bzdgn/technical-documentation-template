Technical Documentation Template
================================
The main purpose of this sample project is to demonstrate the capabilities of spring boot.
Documentation is always a problem in middleware and backend projects. Within the years that 
I'm working, I've seen several different documentation examples and none of them were ideal.
There were high-level design documents, low-level design documents, documents that gives info
about implementation and those give only bird-eye view.

TOC
---
- [0 Introduction](#0-introduction) <br/>
- [1 Components](#1-components) <br/>


 0 Introduction
---------------
As a developer, when there is a new project in backend or middleware, this is how I 
think. I want to know, what the application or module will consume, and produce. In addition to
that, I want to know what will be the additional behavioural effects in between.

Let's give a simple example. A new web service is needed. And the developer is going to implement
it. The documentation should state the incoming message type, like whether it is a json or an xml,
and for each HTTP methods, a request and a response sample. Then just by looking to the sample
input and output messages, developer can create POJO's and write the web service.

Also the tester will use this documentation. But things can get complicated. Like, in between, based
on the payload of the data, let's say, the id of the structure, another web service call can be made,
and several additional web service calls, or database queries can be executed in order to build an
enriched type of data combining the results and translating the message into a more complex type,
then converting it into let's say a json and sending it to a queue, or maybe another database, or
just persisting it as a file.

In this scenario, the documentation should only state the workflow and also the sequence of the
workflow, and explain the effects. Like: A request in XML made, and a response will be immediately
return (an asynchronous call), then web service endpoint 1 and 2 will be called, based on the id
stated in the request payload, and then the output will be written into database and also db id
will be put into a queue.

The reason I'm giving these examples is, I want to demonstrate within this document about how to
make a technical documentation that will give the bird's eye view to the developer and tester.

The documentation must state all the visible behavioral changes and incoming/outgoing messages with
the types, should include all the endpoints used, environmental variables, protocols used, and all
i/o interfaces so that, just looking to this documentation, even a junior developer or a tester
should have a crystal clear picture of the components affected by the system to be build. The 
documentation should be so clear that all the integration tests should be able to be written.
The system will be defined as a black-box, but the behavioral outcomes should be written clearly.

[Go back to TOC](#toc)


 1 Components
-------------

The documentation components will be as follows. Each item should be documentat per operation;

- Input message type and input message sample
- Output message type and output message sample
- In between work flow
- In between work flow tasks
- All the input/output endpoins used
- All the message type and message samples for i/o activity

[Go back to TOC](#toc)


