
# Tutorial 3 - Advanced part 12 - Create a REST API model

[Tutorial 3 - Advanced part 12 - Create a REST API model](https://community.hackolade.com/slides/slide/create-a-rest-api-model-22?fullscreen=1)

## Transcript of the video

hello everyone and welcome to Part 12 of our Hackley tutorial in this part we're going to be talking about how you can use the Accolade Studio to create a rest API model for your apis using a visual and schema-centric approach right so we're going to be developing Swagger or open API specification for those apis without you having to know the Swagger or open API syntaxes right but of course it will help you if you understand and know the features of those different specifications it fits really well with an API first and design first process right which is why we also think that in many cases this type of API development is going to fit really well with nosql data source right access patterns and apis are very often aligned right and the data models that you use in order to fit those access patterns are going to be aligned so therefore there's a natural alignment between API development and nosql data store development right so these things are really fitting hand in glove so it helps a lot to use this type of approach to understand existing apis as well why because you know you're going to be visually representing how the Swagger or open API files actually document the interaction between your software and that API so we can use the Accolade Studio not only to develop these apis but also to better understand them and reverse engineer them into a data model that is much more easier for you to work with we're going to be focusing mostly on open API but the principles behind this will also apply to Swagger the example that we'll be using is something that we've probably all used a URL shortener right a service where you can send a full URL let's say something that you get from I don't know some Google search or an Amazon search or something like that right and that will turn that long URL into a short slug that is much easier to share and copy and paste into into your documentation or emails or whatever right so first we generate the short Slug and then of course we will also be able to do the reverse which is that when we send the slug to the service it will give us back the full URL it's inspired by many of the existing Services out there but shorty was the name of the one that we originally used here right so the output of this effort is going to be a visual description of the API right a visual explanation of the API you know you will see it later on obviously but we're also going to be generating the corresponding API files right the documentation files that described is in a formal way right so you'll see that as well you can use Accolade both to reverse engineer these files or to generate these files based on the model that we create for the API when we design the API then obviously what we're going to try and do is we're going to put our shell ourselves into the shoes of the consumer and make it easy to understand and navigate what this person or this system is doing right and we do that usually with a sequence diagram right where on the left hand side here you see the first process where someone creates an entry using a full URL and receives the short slug back that is generated by the service and on the right hand side you see the second process which is where someone sends a slug through service and gets back the full URL right when we start doing this I would argue that the sequence in which you are going to do this is actually quite important there's a number of tutorials out there that are going to start with the information then generate the paths then generate the components but we actually recommend that you start with the foundation which is the schema that describes the structure of the service and the service contract between producer and consumer so therefore the process that we are going to follow here is that we first are going to create the reusable components which is the schema the request body using the schema the parameters that you're going to use to fetch the full URL from a slug the responses and the oauth to security scheme then we're also going to create the resources with the requests and responses we'll add an endpoint add tags add some metadata information but also make it visually a little bit more interesting and meaningful using color coding and then finally we're going to be generating the open API file with API testing so that you can take this into your development process later on so let's get stuck in let's use the Accolade studio now and start developing our open API so here we go we're going to create a new model and that new model is going to be an open API model obviously the first thing that we're going to be doing is we're going to be creating some reusable components and we have the structure laid out for us here already we'll just give it a meaningful name here and then we can get started and the first thing that we'll be focusing on is of course the schema components we actually just need two schemas one for the happy flow and then one for the error messages so let's add those just adding an object over here that's going to be my URL object and then in that URL object I will be creating two parts to it one of them being a string and that will be my long URL and the other one is going to be also a string and that's going to be the slug that we need over here you know here I'm going to be adding another object right I'm going to recreate another object over here which is going to be my error object and the error object is going to have the first field that is a number and that number is going to be a float that is a status code yep and then I'm going to add one more here which is a string that is going to be the message right so with that we have the first schema components ready for our Exchange you also note that if you have any kind of experience already with complex schemas defined in other Accolade Target data models you can also reference those as external references so that they can be kept in sync with the master version for higher data quality and consistency the next thing that we're going to be doing is we're going to be creating the request body right and that means right clicking over here and then it will actually generate the structure that we need uh as a template that is created to guide you through this entire process with standard media type and applications and all of the structure so let's edit this the first thing that we'll do here is we will rename this as the URL body and then also we will replace the schema here with an object reference of a schema component that we created earlier right so we do that over here by repo replacing this with the URL component that we have and therefore this edits this in the way that you see over here now you may wonder why the slug is also in the request body well that's because of a feature of the sphere of the service that is to allow the end user to specify a preferred custom slug as well as a random system assigned slug to allow the uh the former we need to provide a field for it along with the long URL another advantage of this is that the same schema can be used both for the request and for the response we also want to use give our users the some examples to better understand how to use the API for example with the summary right so here we add an attribute which is an example attribute and this will be a custom example right and here we also add another example which is a random one right so we can we can add these right and you can add values to them where necessary so that's it for now it's also possible to create multiple component request bodies to pick from in your requests next we will follow a very similar set of steps to create the parameter that will be used in the Second Use case when submitting a slug in order to retrieve the full URL here we will choose a path and in other apis you might also choose a query or a header or a cookie so here's how we do that right we just add a path parameter here we will call this the slug right and that will have a schema a content and examples associated with it as well next we are going to right click the responses component and add a response template here right so here we go and that will be how we create a response structure we're going to start with a good response which is 200 okay right we will give it a description here which will be successful operation right apply that and then we also will be clicking here on the schema box and replacing that with the uh schema that we referenced earlier right so we're going to be saying okay replace this with a component which is the one that we had earlier so now we have that component schema referenced as you can see and we will do something very similar here for the generic error message right so this is going to be our error message and the similar thing to do here is to go to the schema and to replace this with a component which is the error component that we had created earlier right so that's it we now have our responses set up and next thing we're going to be doing is we're going to be specifying the security scheme for our API and we'll use the oauth 2 mechanism to uh to do that so here I'm going to add an attribute which is going to be a security scheme right and that is going to be my all auth2 and I can actually go in here and specify the subtype and add a few flows here like for example the authentication codes you know I can add the authorization URL and the token URL here for example so just copied those in there and I can also add the Scopes here right so this one will be the Slugs uh and then um from there on we can actually proceed by creating uh Resources with requests and responses which is what we're going to do next so we're done now with the creation of the reusable components right and so now we're going to switch to our API model and assemble these components into resource paths right so we do that over here we're going to add a resource right and we're going to give that a name right so this is the URLs resource path and we're going to be adding a request in the Box here right so the request here is going to be a post request right so I have to select that over here and then we can start editing that over here right so we can edit the description here shorten a URL for example right and also we can add some responses here right so I'm going to add a couple of responses here so this one over here is going to be our 200 okay response right and then I'm going to do something similar here I'll add another one and which is the 400 response right so bad request and I'll add one more which is the 403 right so I'll select that over here forbidden right and now we already have a nice little structure that we can proceed with it's also a good practice here to add a tag to our uh our post here so we're going to call that the URLs tag here let's write that correctly I know the easiest way for us to create the structure of a request is to go into a dedicated tab right where the template is automatically created and there are obviously different ways to build a request all represented in the template in our case we will be replacing the schema object with um a reusable component that we created earlier by now going here into the schema right and saying you know I'm going to replace this with the URL body right so it's this one over here I'm going to replace it with the component right which is the URL body right so now this uh URL body is actually going to be the request body for this particular request we also created the examples here of a custom Slug and a random slug which will help the developer visualize the possible inputs here and by the way if you ever need a request body here that or response that is different from its original definition you can actually break the link with the definition by right clicking there and choosing here replace by attributes right so then you can do your modifications but you should also be aware that the object will not no longer be updated if the original component evolves now let's go back to our responses over here and we'll start editing those a little bit right so it's easier to just open those up into a separate schema tab obviously right so we'll go right here and edit the schema that I have over here right the schema over there we should reference that replace it by a URL component right so that's the URL component that we need here the long URL and the slug right and we'll do something similar here a little bit lower as well we're going to go back into our 400 here as well and update the schema for that because that's an error code right so we're going to be replacing the reference here right we're going to go back again to the 403 right and edit that schema and replace it by a component as well right which is going to be the error component over there right so that's uh that's all quite easy right if we now get out of these tabs and go back here then we have our resulting API that is visually uh quite understandable I can actually go here and make it a little bit more appealing by saying well this is the positive one right the 400 is the negative one right and the 403 yeah let's give that an orange color because that's uh the security forbidden uh error message isn't it right so that's it we've got a great um API fully developed now for the first use case and we can do something very similar for the Second Use case now so I will start over here and add another resource for that right and that resource is going to be a uh I need to edit it over here right it's going to be the urls and then the slug resource that I'm going to be adding here right in that resource I'm going to have a request right which is going to be a get request right and that get request is going to have a number of responses as well I'll add two responses here right and now this one is going to be our 200 okay and this one is going to be our uh 404 not found right so now we can start editing this a little bit more I'll give this one its appropriate color right so that's the green one and this one is the orange one right so that we make it very clear here and also open this up right and edit the schema for the uh 200 response here right because that is going to be a reference as well to our URL component right so that's uh that's great now I'm going to do something similar to r404 here right the 404 has a scheme is also going to be referencing a component that we already have in place right which is going to be the error component that we already know from our previous work right so now we have the structure of this um resource and it's request and responses responses also in place and you can see how it becomes visually quite attractive right to very quickly understand the exchanges right we can obviously edit this a little bit more but let's uh wrap it up with a couple of finishing touches so I've added a bunch of properties here in the properties tab of our URL shortener and now if we click on the lower tab here we can also generate the open API documentation file on the left hand side we see the generated Json or yaml Syntax for the API that we just created with the application and we also have an onboard validator that verifies the compliance with the open API specification right you can copy the text and paste it into your API process or into your Swagger editor or leverage server and client code generation to make best use of this and you can also obviously forward engineer this right and the forward engineer this into an open API file of your preference don't forget also that this all of this functionality is available in your command line interface right so there's a forward engineering capability in the command line interface that allows you to integrate this file generation into your CI CD pipeline if that would be appropriate all right I think that's it for now so the headset back let's head back to our slides for now great now that we have gone through that entire process I'd like to wrap up this uh Part 12 of our tutorial um and we're going to do that by just coming back to a couple of points that could be important for you um first of all you know we know that the way that we have gone about uh the creation of this API and the way that we've integrated it into a modeling environment May generate some debates you know some people are big fans of code first API development which is obviously not something that we believe is is very helpful we think that design first is going to help you think through all of the details make sure that you understand and discuss all of your Alternatives and different approaches with your stakeholders understand what the impacts are of the choices that you make there and therefore also have a much more advantageous way of developing this API the cost will be lower the quality will be higher it will be easy you to evolve it and hopefully also easier to realizing it to Value right so we actually believe that design first is the way to go about API development and that's why we made the inclusion of API development into our uh hackers your modeling tool such an important part and such an important area of attention you know we believe that there's a lot of people that are supporting this and therefore we warmly recommend that you read up on it and you know there's a couple of Articles linked here but we're also going to refer you back to you know the reading material that we also always include at the end of this these tutorials uh you know there's a lot of great documentation on our website a Blog we have a fantastic book out we have LinkedIn and social and Twitter pages and we highly highly recommend that you take a look at it yourself don't believe a word for it and download the Accolade studio and get going with it if you would have any questions then obviously reach out if not I'm going to thank you for paying attention to this tutorial and wish you a wonderful rest of your day bye