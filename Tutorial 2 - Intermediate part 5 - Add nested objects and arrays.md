
# Tutorial 2 - Intermediate part 5 - Add nested objects and arrays

[URL of video: Tutorial 2 - Intermediate part 5 - Add nested objects and arrays](https://community.hackolade.com/slides/slide/part-5-add-nested-objects-and-arrays-12?fullscreen=1)

## Transcript of the video

hello everyone my name is Rick and I welcome you to part five of our Hackley tutorial in this part we're going to be talking to you about how you can add nested objects and arrays to your data models in previous Parts we've talked a lot about you know how you do create a data model and how you can work with Json and Json schemas to create query driven data models based on access patterns right so we've got our first data model and now we're going to be adding these new nested objects and arrays to that data model that's quite interesting right because these nested objects are actually really complex data types like complex data types I can take many different shapes that are typical of some of the newer nosql type of Technologies right all of these data types are available in the specific plugins and targets that you're going to be using in the Accolade Studio depending on the one that you choose right some technologies will support it others may not right sometimes this is also something to take care of the naming is just different so you know you will have to kind of get used to that and do the specific activities for the specific models but why don't we just Dive Right In and get going with this so what I have here is a very simple data model right where I have a person entity with a first name last name date of birth and height what I'm going to do here is I'm going to insert a new attribute to this particular entity and I'm going to say okay this field is actually going to be an object right meaning that we are going to be adding more depth multiple layers to this particular data element as we add it to the uh to the structure now as you can see I was doing this from the ER diagram but let me remove this quickly and switch to the schema diagram for this particular entity what I'm going to do here now is I'm going to append an attribute here in the schema overview and I'm going to add an object there this object is going to be an address right so let's give it a name and now we can start working with that address and add depth to this structure and adding additional components to the address object that we've just added so what I'll do here is I will add a string here that string is going to be the house number of the address then I'm going to add another one and that is going to be a street right this is the street I'll add another one and that is the city right and I'll add another one and that is the state right note that I have shortcuts here keyboard shortcuts that I can use and by doing that I can build out this nested structure for my particular um uh person entity when I go back here now that you will see that it has also been added obviously to the ER diagram and I have that nested object structure part of my person entity similarly I can also add a different type of complex data type here so if I reopen the person tab here and I'm just going to say okay let's append an attribute here which is going to be an array right then it's going to add a new type of element here which is going to be my pets right so a list of my pets which are going to be a number of string elements that are going to be added over here right I can actually give that a name as well I can say okay I can call this a pet name property right right so and now that will show up over here all the pet names will be added to that other array in a particular sequence I can also use this same mechanism now to add a tuple for example right so I'm going to add another array here right and this is going to be not a string it's going to be in an array as I just said right and this in the Tuple right this is going to be a sequence of ordered items with potentially different schemas so let's say that the first one here is a string right the second one is going to be an object right and then I'll add a third one which is going to be let's say it's going to be a number right uh so I choose that over here right and now I've added that um again two minus the structure let me uh show it to you over here and as expected you know we're going to be uh generating the Json schema for these entities right so if I double click on that you will see the Json here as it gets generated and of course you can use this in a variety of different ways afterwards so there we go in this tutorial we have now reviewed how you can create these more complex data structures with objects and arrays in the next tutorial we'll cover some Json schema choices as well as some conditional applications of sub schemas and pattern Fields I hope this was useful for you and I look forward to seeing you in the next part of the tutorial have a wonderful day