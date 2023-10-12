# Tutorial 0 - Getting Started part 2: Polyglot data modeling

[URL of video: Tutorial 0 - Getting Started part 2 - Polyglot data modeling](https://community.hackolade.com/slides/slide/polyglot-data-modeling-50?fullscreen=1)

## Article based on transcript of the video

Hello everyone and welcome to our Hackolade Tutorial! 

In today's session we're going to be talking about one of the particular introductory topics that I think are very useful for you to get started with Hackolade Studio. Specifically we'll be talking about our [polyglot data modeling](https://hackolade.com/polyglot-data-modeling.html) capability. This is extensively documented on our website. Obviously there are some great articles here that you can take a look at but to give you a quick overview let's go through a couple of slides here. Polyglot data modeling really originated in a discussion and a a lot of deep thought around how to deal with these different levels of data modeling that have been traditionally been used in the time where the relational databases still ruled the world. Right at that time we had these three levels we had conceptual logical and physical data modeling whereby the conceptual and logical levels were always supposed to be technology agnostic.
<img width="1106" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/2a57738a-5987-4312-8d2b-fac436c91747">

However, the _logical_ level was always supposed to be a _normalized_ data model which is in effect a contradiction why because obviously with the advent of all of these new types of data technologies you really can't say that the logical, technology agnostic view of the world has to be normalized! In a new polyglot persistence data architecture you will have lots of different parts to your application, lots of different technologies will work together to compose one particular e-commerce platform for example.

<img width="1106" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/9b96460b-5298-47b4-b9ed-f9368bf31940">

In the 21st century you will have your inventory and your item pricing in the relational database, you will have the shopping cart and session data in a Key Value Store, you will have your product catalog and your completed orders in a document store, etc etc etc ... You can read it from the screen so obviously in this landscape it doesn't make sense to start normalizing everything at the _logical_ level. We will have a need for a technology agnostic view of our data architecture that is independent of all of these different types of data stores on top of that we also know that you know every organization that develops these types of 21st century applications will want to have some kind of consistency across all of these types of data stores which means that they will have to make sure that you know everything evolves in lockstep at the same time and things don't break when the schemas evolve. 

<img width="1105" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/50d3fec1-bc83-49c6-ab46-cabb653e854e">

Therefore organizations are building pipelines right they are building structured ways of dealing with these different types of data architectures and therefore there is an increasing need to have a an overarching umbrella data model for all of your data components. This is why Hackolade has come up with a **polyglot data model** which is in effect somewhat similar to a logical data model but also similar to a physical data model, and it even has some ideas and some concepts of a conceptual data model included in it. A polyglot data model effectively sits across the boundary between logical and physical data models and we sometimes refer to it as a logical model on steroids. It's a logical model with lots of additional functionality: specifically a polyglot data model 
* allows for denormalization at this technology agnostic higher level of data modeling, and
* it allows for complex data types things like nested structures for example
In effect it will represent a common physical model that will allow you to generate schemas, technical artifacts for a variety of different technologies with automated mapping between all the different data types of the respective "target" technologies.

<img width="1105" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/53006e6b-047d-4ac9-8dae-a5fede344c6c">

It also has a lot of functionality that allows you to reuse and leverage a library of canonical objects for your domains so that you can use them consistently across all of your physical data models just so everyone understands. A polyglot data model is an umbrella data model that sits across all of these underlying physical data models, so there's a master data model at the top or multiple Master data models at the top that are driving the underlying physical data models that are specific to a particular Target technology.

<img width="1105" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/1e45f619-6c55-4694-9e9b-855667d786a8">

I think this is a helpful picture because it shows you how you can have multiple polyglot models: a polylot one data model with the blue rectangles, a polyglot 2 data model with the red circles and a 3rd polyglot data model with the green triangles.

<img width="1106" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/29184540-519a-4328-884b-e0aac30287aa">

What you can see at the bottom here is that as you actually derive target models, so physical data models from these different polyglot models, you can mix and match them. You can draw E11 E1 2 and e13 from polyglot 1 but at the same target a physical model include things like E21 and E23! So you mix and match these things together, you combine them as you see fit and you link these different data models together as you need them. This is how you can maintain that governance and maintain that consistency across all of your different data models.

I mentioned earlier that there are some conceptual modeling Concepts in a polyglot data model and that's specifically in what we call the graph view right when you work with a polyglot data model you will see that there are these graph representations of your data model where you can basically have a higher level representation of the entities and the relationships in a model delivered by this graph diagram.

<img width="1104" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/234f0b71-119b-4e37-9a16-f5f1ebcde907">

With that we're going to wrap up this section in our Hackolade tutorial. I would love to refer you to a lot of reading material that we have available for you both online on our blog in the books: we have the mongodb data modeling and schema design book that Pascal Desmarets co-authored, but we have a bunch of other books that are already available on Amazon or forthcoming  very soon. I would love to see you on our socials on LinkedIn on Twitter and of course please [download the Hackolade Studio for free](https://hackolade.com/download.html). If you have any questions please reach out to us we're here to help and I wish you a very happy rest of your day. Thank you.
