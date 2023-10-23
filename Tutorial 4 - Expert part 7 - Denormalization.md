
# Tutorial 4 - Expert part 7 - Denormalization

[Tutorial 4 - Expert part 7 - Denormalization](https://community.hackolade.com/slides/slide/denormalization-28?fullscreen=1)

## Article based on transcript of the video

Welcome to another episode of our Hackolade Tutorial.

In this episode we'll be talking about how you can use Hackolade to suggest denormalized structures in a normalized data model. This can be really useful, for example when you are contemplating to do some application modern modernization. For example, when you are simply migrating data from a relational database management system to some kind of a NOSQL document database or a JSON schema or whatever, it might be that in that case you will be considering how you would design the data model for that new NOSQL storage format. You will probably be basing it on some kind of an access pattern.

<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/cb94dc30-483f-4c0c-ba16-61f5b44e7115">

We have a very good and [separate tutorial](https://community.hackolade.com/slides/slide/part-3-query-driven-data-modeling-based-on-access-patterns-5),  a [separate article](https://hackolade.com/help/Query-drivendatamodelingbasedona.html) about this. You're going to do some modeling that is going to leverage the concepts and the structural denormalized data models in that new modernized environment. So what we're going to show showing you here in this tutorial is that you can use a tool like the Hackolade Studio to implement that denormalized structure. It's very important, however, that you realize that this is something that you should be thinking about up front. You don't do this randomly, you don't do this haphazardly: you would do the denormalization in a very structured way based on **the analysis of your access patterns**. 

What we'll be showing you a little bit later is a an example of the Northwind database. 

<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/74ea3027-1269-44d8-8190-1f4b139f908e">

You probably noticed from many demo databases that you've seen over the years where you have an `orders` table right with all the lists of the orders, row by row, and then an `order details` table where for every `order_id` you would have a reference to a `product` and a `quantity` of that order line, as it would appear on the order specifically. This is an example of a set of tables that contain a _foreign key relationship_, and that you could potentially denormalize.


Therefore in the Hackolade Studio we can help you do that denormalization, but you should really take care while doing so. You do this two tables at a time.

<img width="1110" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/8d1f2e70-3713-4a18-9380-efbf817977df">

You don't try to do more at the time. You have to specifically select what type of embedding you want to be using in your denormalization: there are different ways that you can do this depending on the direction and the cardinality of your relationship. In one direction you might be able to say "sub document in child", in the other direction that would most likely then become "array in parent". You can also consider implementing both, if you are implementing the extended reference pattern for example. You can also edit this when necessary.


So let's take a look at that.
* in the one direction right where you would be embedding an array in the parent: you can see on the left what the current structure is in the normalized data model, and in the denormalized data model you would modify the `orders` entity to have a an array of `order_details` listed inside it. That's the resulting denormalization right.
<img width="1109" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/dfc4a441-979f-41dd-92ef-c25d7ba46c73">

* in the other direction, if you would like to be embedding sub documents in a child, then what happens is that in the `order_details` collection or entity, you would all of a sudden have a list of sub-documents where the products would be contained. This is how the resulting denormalization would play out.
<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/c79c8617-034c-4669-b7e6-3e8817ce5d1d">

I'll switch to my Hackolade environment now and show you how this is done.

So here we are we have the north wind data model: the normalized version of it, where we have the `orders` entity and the `order_details` entity. They are linked to each other through this relationship.
<img width="1111" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/7af9f668-9f8b-464b-b233-82a11dd1fc96">


What I'll do next is I'll go to my tools menu and say why don't we suggest the denormalization. Then I select the two entities involved: I select two entities at a time, and I say okay let's do a _"sub document in child"_ first. 
<img width="1109" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/42321260-c83a-4430-8cb3-f1f370727c1d">


When you do that you see that what is what has happened. Now we have modified the order details table here and it now has this nested structure where the product details of the orders are included inside this entity. That's one way of doing it.
<img width="1110" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/3f9eb7af-a1da-4e70-abd5-dfd09879f075">

Let's go back to our original original structure. Now I'll do the other direction: I'll basically do the denormalization the other direction. We say: why don't you do this right _"Array in parent"_. 
<img width="1110" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/48cb921d-c8ce-4a93-a4f0-c0f2367b2b12">

In my view this is actually a little bit more logical, because then what in the orders entity you would have all the order details embedded inside that document. That's really logical and two great examples of how you can use the Hackolade Studio to suggest denormalization.

Let's wrap this up here. I would highly recommend that you would read up on this: obviously you know [our documentation](https://hackolade.com/help/Whatisadatamodel.html) or [Blog](https://hackolade.com/blog.html) the excellent [MongoDB data modeling book](https://www.amazon.com/MongoDB-Data-Modeling-Schema-Design/dp/1634621980/) - which is particularly relevant here because the patterns that are one of the one of the coolest parts of this book. Definitely take a look at that. With that I'm going to wrap up this tutorial and wish you a wonderful rest of your day. Thank you very much.
