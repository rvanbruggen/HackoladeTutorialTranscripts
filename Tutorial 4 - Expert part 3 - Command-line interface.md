
# Tutorial 4 - Expert part 3 - Command-line interface

[Tutorial 4 - Expert part 3 - Command-line interface](https://community.hackolade.com/slides/slide/command-line-interface-21?fullscreen=1)

## Article based on transcript of the video

### Part 1: Reverse Engineering

Welcome to another Hackolade How-to video. 

Today I'm going to show you how you can use the Hackolade [command line interface](https://hackolade.com/help/CommandLineInterface.html) to automate some of your most common tasks in your data modeling workflows. There's a lot of different things that you can do with the command line interface and today I'm going to actually show you how you can reverse engineer the data model from a particular Target. 

What I want to show you here first is doing it using the tool using the Hackolade visual tool where I'm going to point it to a postgres database. I'm going to say okay using this particular connection "HackoladeLocalPostgres", please import the "DVD rental database". Not just import it I actually just all I want to do is inspect it and derive the schema for it.
<img width="1231" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/c7ac1c8c-ba65-4074-b2fd-4306c1ccc654">

This takes a couple of seconds so I'm going to come back to it when it's finished and show you what the model will look like. Here we go:
<img width="1233" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/88b81ef6-5f25-44f9-9970-7952c444f0b0">
The process has finished and now I have my Hackolade data model already. It's got the films, the actors, the languages - all of this is available in this data model that was reverse engineered. I'm going to call this the "manual model". I'm going to save that in my CLI directory, and then I will show you as well how you can actually do this differently by using the **command line interface**.

In order to do that I'm going to switch to my terminal right, and I'm in the terminal I'm going to paste a particular command right a particular command that says "Hackolade revEng":
<img width="1220" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/a1fefdec-afb2-42d3-b0ab-1bf96ca171f0">

That means "reverse engineer" from a Target called "POSTGRESQL", to a particular file the `CLImodel.json` file, using a connection that was already existing. I actually use that in the tool based or user interface based process as well: "HackoladeLocalPostres". I'm going to reverse engineer a particular database schema for the "DVD rentals". I start this I launch the command and again this is going to take a few seconds so I'll come back to you once the process has finished: here we go the model has been saved.
<img width="1220" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/72650476-1ac9-4e89-92eb-278b9249ea7c">

So if I now take a look here: this is where I originally had my `manualmodel.json` and now I also have the `CLImodel.json`.
<img width="1229" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/611587e5-01bc-4533-affa-60ee3af2d9e4">
I'm going to try and open that. I'll open the model in my user interface right so it's a `CLImodel.json`, it should be exactly the same as what I had before. So it's got the same entities it's got the films, it's got the languages, the actors, exactly the same thing and I can actually do this automatically now using the command line interface, as many times as I want. This allows me to automate my pipelines and make sure that I have an accurate view of the latest state of my schema, of my data model as it is existing in the database. That wraps up this little video. I'm going to come back to some other CLI functionalities in other videos but for now I'm going to wish you a wonderful day and thank you for watching.

### Part 2: Model Comparison

Welcome to another Hackolade How-to video.

In this video I'm actually going to do a sequel to the previous video that was all about how we can use the Hackoalde [command line interface](https://hackolade.com/help/CommandLineInterface.html) to reverse engineer a data model from a particular target, in that case a particular PostgreSQL database. By using that system we actually ended up with two data models: we had one that we created manually, and the other one that we created through the CLI. Now let me open up the CLI version of it because I've actually made a small change to that data model: I've **removed the language entity** from the `film` over here, which basically is a fundamental change to the data model that we may or may not be able to detect automatically. What I'm going to do now, is I'm actually going to do a comparison of the two data models:
* the left model will be my um manually created model which I created with the tool,  and
* the right hand model will be the one that I created with the CLI, and which I adapted afterwards and removed the language entity from.
<img width="1232" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/7cef48b2-1aea-46aa-ad95-172ff6ce6b40">

I should actually add here that the order of these two models left or right is very important right because if you put one model or the other model to the left, or vice versa you would actually get very different Delta models and very different operations to go from one model to the other. The difference between the models would either be a _creation_ or a _deletion_  depending on the order of these two models. Let me do that manually here: I'm going to compare it.
<img width="1233" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/72e00c6e-6bdf-4c2a-b70b-b09f3ecbad37">

It does detect that there has been a change in the language entity and what I can do with Hackolade I can generate this Delta model right which I'm going to do here as well: so it's the CLI model Delta that I'm going to create. I'm going to do this as a Json document right and it's going to be generating that Delta model for me, and I can then immediately open that, and take a look at that over here in my Hackolade client, and then you will see exactly what it is: the language has been deleted. Language entity has been deletedl.
<img width="1232" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/895a6cc3-156c-467c-b591-7153473e5a25">

I can then also look at the PostgreSQL DDL ALTER script that has been generated by the client:
<img width="1232" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/0f8788df-731f-47a0-a566-04cc3be7a699">
I can then, if I wanted to automatically, execute that in my PostgreSQL management console.

Now the interesting thing here is that I can also do that exact operation just like I did it today in the Hackolade Studio client, in my Command Line Interface. That's exactly what I'd like to show you now. I'm going to switch to that command line interface and show you how I can execute a few commands and then do exactly the same operation. So let me then find my terminal and then I'm going to paste the script.
<img width="1219" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/c54302c9-e145-454b-a779-e7c12bb996d0">

So this is exactly the same command but instead of doing reverse engineering it do it's doing a `compMod` - basically a comparison between the manual model and the CLI model that I have in my directory. It's going to generate the `deltamodel.json` file for me. Again: this is exactly the same thing as what I was doing with the tool visually but now through a script - something that I can put into a pipeline, something that I can trigger automatically. Now all I need to do is go back to my tool open the model to open the Delta model that's this one over here right and you will see that it contains exactly the same thing right: there's a language deletion here. We've also generated the ddl script right so that's it I wanted to show you.  I hope that it was useful: this was the second step of our CLI video how to's, where we showed you how you can take the reverse engineered model from before and do a model comparison and do that also automatically using the CLI. I hope that this was useful and I wish you a wonderful day.

### Part 3: DDL script generation

This is another episode of our Hackolade how-to videos.

This is going to be a very short one following up on the previous video that we did around using the [command line interface](https://hackolade.com/help/CommandLineInterface.html) to compare models and generate a Delta model I have that Delta model right here.
<img width="1232" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/73f67b61-b600-42cd-8c4f-f732ef62174b">

As you can tell this Delta Model was identifying the fact that an entity had been deleted: specifically the language entity had been deleted. There's a PostgreSQL DDL script that was generated inside the tool, but what I want to show you now is that you can do exactly the same thing in our command line. So what I'm doing here is I'm pasting a little command here which is the Hackolade command line interface that will forward engineer this Delta model that I have generated already, into a script.
<img width="1222" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/a6d2ed98-4ce5-445e-aaa4-16fe96a1c78c">

It's going to create a script for me, and this script is going to be exactly what I need to automatically update my data database schema using an automated process. So let me go into my directory here. You see that there's a new directory called Deltamodel.script right and when I open that it will show me that there is a new `.sql` script that drops the table if it exists.
<img width="1232" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/b20406d7-f321-4198-8c65-907bb1585326">
This is exactly what I was hoping. Great! That's what I wanted to show you, you can not only reverse engineer using the CLI, not only compare models using the CLI but you can also generate the scripts that you want in order to manage the schemas on your database. I hope that this was useful and I wish you a wonderful day.

### Part 4: documentation generation
Welcome to another Accolade how-to video.

This is going to be another short video where we explain how you can use the [command line interface](https://hackolade.com/help/CommandLineInterface.html) to generate documentation automatically for your data models, using the command line interface. This is something that you can do very very easily using the tool also. Obviously if I open up a data model right at the top here I will have a a particular menu item that allows me to generate the documentation.
<img width="1233" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/376959d8-aa1f-4586-a554-be102d0754b7">

If I do that then after a few seconds it will come back with the HTML PDF or markdown documentation. But I can do this automatically by just feeding a simple command to my terminal here.
<img width="1220" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/2afd2b41-9561-4f08-9ab0-4c8e244ca61d">
This one here is the Hackolade `genDoc` command, and I'm going to first generate HTML right and then we'll take it from there. So that's the first one that I'm going to take and that should only take a few seconds and it should come back with the directory fully generated. Note that this HTML version of the documentation is actually quite smart it includes all of the visuals, all of the graphics immediately. 

Now let me do the same thing with the PDF format:
<img width="1218" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/64f8bfd3-559a-4f69-83c0-7716959f7afa">
So I'm going to generate that as well, and last and but not least I will do the Markdown generation as well, and then show you what it looks like once that is all finished.

It's a very very simple set of commands that you can generate here and again the same principle applies to as to all of the command line interface commands. You can very very easily integrate this into a script or a GitHub action or whatever. Just showing this so right here right so we've got the documentation directory right here the PDF is already there right the HTML is already there right and in a few seconds we will get the markdown also to be generated. The markdown is also really interesting because it includes a separate directory with all of the PNG files: all of these things are automatically put into a separate directory, so that you can also use them for other purposes where necessary.
<img width="1233" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/54d7c1b7-0f43-44a7-9bcc-ca3d5171b2f9">

So again everything that we were able to do in the client interface of Hackolade we're also able to do as part of the command line interface and as a consequence we can embed that into all of our processes, into all of our pipelines and automate some of our data modeling tasks using this command line interface. I hope this was useful and I look forward to hearing from you and I wish you a wonderful day.

### Part 5: simulating automation in a script

Welcome to another Hackolade how-to video.

In this video I'm going to try and tie together the different aspects of our [command line interface](https://hackolade.com/help/CommandLineInterface.html) that I have them demonstrated in previous videos. What I'm going to do here is I'm going to try and create a very simple way that will show you how you can use the command line interface to automate automate some of your workflows. What have I done I've basically created a new little document over here, which is a script. A shell script:
<img width="1229" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/1c3cb486-ca4c-471f-be6e-be55ae61fb95">

You have the same thing on Windows or other platforms: a batch file or whatever you want to call it that will automate the execution of all of the different steps that we had in our previous videos:
<img width="1233" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/0873a445-f48a-4487-b78f-509e5ae7bf6c">

1. So first of all we're going to reverse engineer a postgres SQL database, then
2. Secondly we're going to compare that model that we have generated from the reverse engineering with a previous previously generated model, and then
3. we're going to create the ddl script, and
4. finally generate the documentation.

This is a very simple shell script. I am not a bash programmer as you will see, but still this thing can and will be called from for example a GitHub action or some other trigger and it will basically do everything that we want it to do.
<img width="1154" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/51fe5ec5-584d-4452-a98f-1c3b48d48b6c">

So first step here we're going to reverse engineer a postgres SQL database into a calculated data model. I'm going to pause the recording here for a second and here we are. We've gone to the next step already the reverse engineering has completed and it has saved the model uh into the directory and it's already started the second phase right it's uh compared that model to the previous model and it's also already started the third step which is it's generating the ddl script for my comparison model.
<img width="1221" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/2e99ad3f-c312-4d6c-bb92-5c3f64d940f7">

The fourth step has already started as well:
<img width="1220" alt="image" src="https://github.com/rvanbruggen/HackoladeTutorialTranscripts/assets/2995654/45d100f7-d8af-4865-a590-8f951fcf5016">

It is generating the different PDF, HTML and markdown documentation artifacts. PDF is you know what it is - it's a PDF document. The HTML document is super interesting because it includes all of the graphics into one comprehensive document. And the markdown is interesting because it will have all of the graphics put into a separate folder where all the `.png`'s are there for you to use and integrate it to other systems. 

So this is all going completely automatically you know in one simple shell script. Nothing that you have to do in order to trigger this you know you can call this from wherever, and as you will see here you know the directory is already here right so I've got the the documentation directory filling up nicely.

This is how you can work with a simple shell script to automate your pipelines. Much more sophistication is possible there but I hope that this was already useful and that you will enjoy this using this in your workflows.

I wish you a wonderful day.
