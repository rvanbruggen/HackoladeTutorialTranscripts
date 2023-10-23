
# Tutorial 4 - Expert part 8 - ER Diagram Views

[Tutorial 4 - Expert part 8 - ER Diagram Views](https://community.hackolade.com/slides/slide/er-diagram-views-29?fullscreen=1)

## Article based on transcript of the video

Welcome to another Hackolade Tutorial.

In this tutorial we're going to be talking to you about what we call **ERD views**,  _entity relationship diagram views_. This is a topic that's really interesting. It's a very short topic, but what we'll talk about is how you can actually use ERDVs to make sure that specific parts of your model - sometimes you have a really large model with lots and lots of entities and lots of relationships between those entities - can be divided up, can be split up into things that we sometimes call _subject areas_, or _domain diagrams_. ERDVs are the tool to use for this. 
<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/063b0645-7f1d-4838-b846-f523ce9dc1b8">

We're going to be selecting a subset of the entities of the main entity relationship diagram, and split it up over multiple different ER diagram views - so that you can better manage those really large models. This will allow you to split up the model into domains. By domain or by subject area. It is a really great tool for implementing this idea around [domain driven data modeling](https://hackolade.com/domain-driven-data-modeling.html) that we've been talking about quite a bit. This is one of the tools that you can use for this.

Entities can appear in multiple ERDVs, including also relationships. You can make modifications in the ERDVs and they are immediately reflected across the different parts of your model. Wherever you edit it, it will immediately be reflected in the UI. Another really cool feature is that you can actually configure different display options for every different ERDV, so you can have different ways of looking at that subject domain. 

You can create an erdv from the actions menu, from the toolbar, or from the object browser.
<img width="1108" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/abdee2fb-52db-4248-b77f-c0658174293c">

Of course you can always edit this right you can always edit how you can see which parts of your main ER diagram are part of specific domain specific ERDVs. 
<img width="1109" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/bc1ab426-6918-446b-bf8e-8d728180d26e">

What I have here is you know a very modestly sized relational database diagram. It's a PostgreSQL database, and you can see here there's different entities:
<img width="1109" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/d7c52594-4961-439e-ac06-919ddf07785e">

This is the DVD rental data set that I've been using quite a few times.You've got the rentals, you've got the staff, you've got the inventory, you've got the payments. The first thing we'll do here is we will select a few of these entities: hold down your control key and select multiple of these entities. Then let's add them to a diagram view:
<img width="1110" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/6ba06c0a-5d8c-4d0f-87bd-1ddecb3a340b">

I currently don't have any diagram views set up yet so I'll create a new one. You will see that at the bottom of your object browser all of a sudden this is now appearing. 
<img width="1109" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/754f57b9-04bc-4fd3-aa2a-40338c36a8d8">

I can play around with this, I can also make some edits. here right so here I have this property called `nickname` in the `staff` entity. Let me just remove that I'm removing it from the ERDV that I've just created right and if I now switch back to the main ERD, then you will see that in the `staff` entity over here there's no longer a `nickname` property. 

If I add it back here and I call it a `fancy nickname`, a new property that I've just added here:
<img width="1110" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/170d988c-d5ff-4169-8c8a-f83818d9b6b4">

When I switch back to the ERDV and you will see that it is already there:
<img width="1110" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/43dd85e8-ee36-41a3-8277-168a74593fce">

I can also add another one. I can add another ERDV I'll go back into the DVD rental, and I'll say `inventory`, `rental` and `staff` - so not the payment. I'm going to add to an ERDV and I can create this inside the already existing new diagram view, or I can create another one which I'm going to give a name, just to not be too confusing, `2nd new diagram view`. Now you can see them appearing: I've got the new diagram view over here maybe I'll just rename that and say this is the first one. I've got the `1st New Diagram View` and I've got the `2nd New Diagram View`. You can see here in the `2nd New Diagram View` I also have the `nickname` available but I can now say well you know what in this `2nd New Diagram View` I'd like to have a little bit of a different way of looking at things. 
<img width="1107" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/88057afa-d912-43ac-a85d-6dd2b9a604d1">

So let me just just get rid of all of those different attributes. Switching between those diagram views and the main ER diagram you will see that they look quite different. I can also go and edit the membership of the diagram view:
<img width="1109" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/91069a28-b9ba-4d42-87f5-ffd7c174ff9b">

If I go over here I can now say, in the schema there's 15 tables with only three of them are in that second diagram view, why don't why don't I add one here - the `country` entity. That will now also show up here. I can obviously restructure that so that it becomes a little bit more visible:
<img width="1110" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/cd5f2eb6-97c3-469b-a8a1-45e0cdd00d14">

That's the overview that I wanted to give you so with that I'm going to wrap up this tutorial and highlight a few more reading materials. I've been highlighting these throughout our different tutorials: some [great documentation](https://hackolade.com/help/Whatisadatamodel.html), a [great blog](https://hackolade.com/blog.html), a fantastic [new book about MongoDB data data modeling](https://www.amazon.com/MongoDB-Data-Modeling-Schema-Design/dp/1634621980/). There's another one around [Neo4j data modeling]([url](https://hackolade.com/books.html)) and many of the concepts that you will find in there are applicable to lots of other domains as well.

With that I'm going to wrap up,  and I'm going to wish you a wonderful rest of your day.
