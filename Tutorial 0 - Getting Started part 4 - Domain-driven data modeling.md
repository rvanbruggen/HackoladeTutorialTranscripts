# Tutorial 0 - Getting Started part 4: Domain-driven data modeling

[URL of video: Tutorial 0 - Getting Started part 4 - Domain-driven data modeling](https://community.hackolade.com/slides/slide/domain-driven-data-modeling-52?fullscreen=1)

## Article based on transcript of the video

Hello everyone, and welcome to our Hackolade Tutorial!

In this part of the tutorial we're going to be explaining some of the fundamentals of the Hackolade product set and we're going to do that by explaining some of the main concepts behind it. We've already talked about [polyglot data modeling](https://hackolade.com/polyglot-data-modeling.html) and [metadata as code](https://hackolade.com/metadata-as-code.html) in separate videos, but in this video we're actually going to talk about an overarching concept that we've recently published about which is what we call [domain-driven data modeling](https://hackolade.com/domain-driven-data-modeling.html).

The reason why we've come up with this new concept is that we wanted to explain to people why some of these fundamental concepts you know like polyglot data modeling or metadata as code, why they are so important and why it's so interesting to apply them in a real world context. Specifically we also wanted to make people understand that domain driven data modeling is a solution to a problem that many of us have encountered in complex data modeling exercises: sometimes people try to make these data models too large and too complex, and that makes them counterproductive. They very quickly start looking like a big ball of mud.
<img width="100%" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/b59aeef7-8ca7-49a4-a42d-3fa533f9bf9e">


This ball of mud leads to so many pointless discussions between different stakeholders in your organization that it can really lead to massive project delays and we want to help you solve that. We want to make you understand that there is a different way to do this, that smaller manageable data models are actually the blueprint for modern complex applications.

<img width="1107" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/271cbe8b-c06b-4359-9ce9-06d71c8c7edf">

Please also think about this as how you work with industry data models. Industry data models are often an example of how people make these problems too large, too big, and they apply them in the wrong fashion. So let's dig right in: we're going to talk about some of the main principles that we think are part of **domain driven data modeling**. This is heavily inspired by [domain driven design](https://en.wikipedia.org/wiki/Domain-driven_design), which is a fantastic application to software development practices. Some of these concepts we're applying to the data modeling domain.

<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/17b6f3ca-0d56-4421-9643-eeeaf460505a">

1. The first principle that we're going to be talking about here is how you should really **focus on the core domain**. You really want to concentrate your efforts for maximum impact and really limit the scope of your data modeling exercise as much as you possibly can. Don't make it too big, don't make it too complicated - really focus on the core.
<img width="1105" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/ee05d510-2073-4913-8ae6-335d32a9356c">


2. The second principle is that in order to be able to focus on the core you actually need to **break down complex problems into smaller ones**. We call this a bounded context. We create these limited domains that you can focus on that you can really solve the one problem at a time. Obviously you still need to be able to keep the bigger picture in mind and make sure that the bigger problem also gets solved, but the way to get there is obviously by tackling this complexity one by one.
<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/93d02a0f-7641-438b-b519-aa47051587da">


3. The next principle that we'll talk about is that really when you talk about data modeling you're talking about applying a **communication tool** that allows people to understand what the data that they are working with actually means and what the context is that they are working in. That's the core function of data modeling and that means that you have to start using a **common vocabulary**, so in your data model, as you use it as a communication tool you really want to focus on making sure that everyone understands and everyone uses, and you promote this common vocabulary.
<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/c4b62fd8-e53e-420c-945d-a566a30b81d4">


4. The next principle that I think we should all learn from, is that it becomes much easier to work with data models as you are able to aggregate related objects together. This is a lesson that we've learned in other fields, specifically the data engineering field, where things like **nosql databases** have sprung up. New types of databases have sprung up that really promote this as well: work with "aggregates", work with related objects that are construed of a number of different other objects so that they represent the business entity that you are working with. Cluster these things together if they belong together.
<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/749caf77-72ff-4bb5-926f-8ff0bedbdf24">

Obviously this means that you also want to be breaking up the problem into bounded contexts (see above).

5. Another principle that we think is a core part of domain-driven data modeling, is the collaboration aspect of working together between technical staff and subject matter experts to reach a shared understanding.
<img width="1109" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/52dcbcf4-7a91-47c5-b377-588eeb324146">
You really don't want to have a conflict situation between the subject matter expert or business user, and the data engineer. No, you want to use the communication tool that data models represent to reach this shared understanding of what the problems are that we're trying to solve.


6. Again, as we break down the problem into smaller parts, it makes total sense to take an iterative approach to the development of your data models and your applications, which is a core element of Agile development so that you can really create this solution step by step refine it as you go along. Evolve it as you go along and develop a richer application step by step.
<img width="1103" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/a56cc224-4c98-4b62-ba86-11c44e80b115">

All of this relates to the core of what we try to do with Hackolade: **we try to reconcile business and IT through a shared understanding of the context and the meaning of data.** 
<img width="1105" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/e179da8d-2d65-493a-8a84-4dd78a9abdab">
That's the core mission of what we're trying to do with Accolade and some of the tools that we develop are obviously related to domain-driven data modeling: polyglot data modeling has a core role to play here, as has metadata as code.

Polyglot data modeling provides this technology agnostic data model that allows you to generate physical schemas for a wide variety of different targets. There's a separate tutorial on this topic obviously, but please understand that this fits into the domain-driven data modeling approach.
<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/a470b991-4397-46e4-a467-07044b438ce4">
Of course metadata as code is going to co-locate the code and the data models so that there is a **single source of truth** for Business and Technical stakeholders, so that the subject matter experts and the data engineers are always looking at the same artifacts. 
<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/d779da3d-2215-493c-8618-2457cd70bc4c">

This is how you achieve domain driven data modeling. We've actually provided people with a really nice infographic which we will obviously sharing later on and which you may recognize a little bit from our presentation here - so please take a look at that.
<p align="center" width="100%">
<img width="50%" src="https://hackolade.com/img/dddm-infographic-750px.png" align="center">
</p>

Also don't forget that we offer a wide variety of reading materials online on our [blog](https://hackolade.com/blog.html), in the [books](https://hackolade.com/books.html) - there's a wide variety of books these days on specific data modeling techniques like MongoDB data modeling, but also for Neo4j, Oracle 23C, Elasticsearch - and there's more coming in the near future. Please follow us on the socials as well and always remember that you can always try Hackolade by [downloading it yourself and giving it a spin](https://hackolade.com/download.html) thank you for paying attention and I hope this was a useful session and I'll wish you a wonderful rest of your day.
