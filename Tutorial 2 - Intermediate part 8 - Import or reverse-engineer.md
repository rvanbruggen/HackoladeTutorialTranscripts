
# Tutorial 2 - Intermediate part 8 - Import or reverse-engineer

[Tutorial 2 - Intermediate part 8 - Import or reverse-engineer](https://community.hackolade.com/slides/slide/part-8-import-or-reverse-engineer-15?fullscreen=1)

## Transcript of the video

hello there and welcome to part 8 of our hack Elite tutorial in this part we're going to be talking about how you can use the Accolade Studio to import or reverse engineer um your data models right so that means that you're not going to start from scratch you're not going to be creating objects and relationships and all of those types of things like we did in the previous tutorials but we're actually going to do that based on something that is already there based on an existing data structure right so we're going to import these structures into our Accolade data models right it could be existing data models or they could be new data models and the reason why we do that obviously is because we're not living on an island you know no database and no data model is an island we need to be integrating with what we already have it's not a green field and we're going to use that for our modeling and documentation purposes right so and then once we have that once we have that reverse engineered structure we can start and do more work on that right we can we can add those descriptions constraints we can evolve the schema we we can share it with other people using dictionaries and we can integrate it into all of our other processes right now what's important is that you understand what are some of the different sources for our reverse engineering capability and there's quite a few right there's quite a few different types of sources that we could start from and you will see it when you start working with the tool it depends on the type of Target that you choose but in um in in in every Target you will have a choice of different reverse engineering sources it could be a Json document or a yaml document could be a Json schema or EML schema could be ddls right ddl files that you get from a wide variety of database systems that know and work with ddls like for example Oracle or SQL server or db2 right whatever it might be could be an xsd schema this is super interesting because many other modeling tools allow you to export their data models into an xsd schema an XML schema definition so that's really interesting you can start from there you can also start from an Excel file template and you know we all know you know the world that would fall apart if we didn't have integration of it systems based on Excel well that is also true for the data modeling World many bulk update operations or any kind of integration operation is actually based on an Excel template Hackley has a template that you can look at and that you can use for automatically importing stuff into your data model then of course we have Target specific instance reverse engineering which means that you can actually connect Accolade through its plugins to a particular database or a schema file or schema registry or a cloud storage environment and then say okay pick me up what you have there pick me up what you find there and integrate that into our model and then last but not least there's a really important source that is making more and more Headway these days which is a data dictionary as a source for reverse engineering like for example collibra but there's many many other like that out there so let's take a look here you know let's take a look at file based reverse engineering processes right so you can select one or more files right that um you can choose from and then these files will be read by hackerlaid and it will then import what it finds in those files as entities in your entity relationship relationship diagram right so you can also choose to import it as model definitions right so you can then use them yourself at a later Point as you know as you work with these definitions but the most common use case would be that you import it into your ERD when you do that it will also try to assess the tool we'll try to assess you know what's already there in your model and see if it needs to be creating a new container or a new set of entities or if it needs to merge it into those existing entities right really interesting feature I think is that when you import nested structures like for example a Json document right uh or you know you start from you know a mongodb database or whatever and you uh import that into a normalized target for example a relational database system then we can apply the rules of normalization for you and automatically apply that and apply that uh during your reverse engineering process reverse engineering instances are a little bit different right so this means that you're not you know reading a file from your file system or even from your GitHub repo you're actually going to be connecting over the network to an instance on-prem or in the cloud using a set of connection parameters right and then you're going to read from those instances and automatically create your data models from what it finds on those instances um also important you know both the file based sources and the instance-based sources that you have available to you for reverse engineering are also available from the command line interface right so that means that you can automate it you can put this into your CI CD pipelines from a Docker container for example and have that run on a 90 basis and automatically reverse engineer whatever it is that you have in your data stores so that you can also compare it to what was there yesterday right and see if there's any changes that should or should not have been applied to those systems great I'm going to take a moment now and show you how you can work with these different resources so let's go to the Accolade Studio so let's start here right we're going to create a very simple model for a Json document right but we're actually going to say okay well I already have a Json document so I'm going to reverse engineer what I already have which is uh here in my file system and create documents in the ERD from what I find right so you know if I do that it's going to start reading that Json document and create a model for that existing Json document as part of my schema here right so it's as simple as that you know you can do this with lots of different file formats right so I can also grab a parquet file or an Avro schema or whatever it might be and do exactly what I just did here now I'd also like to show you how you can do this um a little bit differently when you have that same Json file but you want to uh reverse engineer that into something different like for example a postgres database right so if I reverse engineer it that same file into a postgres database then it's going to allow you to normalize that file automatically right so here I'm going to create tables in the ERD but I'm also going to normalize complex data types into separate entities so it's exactly the same file nothing has changed to the file right but when I do that reverse engineering you see that it comes up with a quite different model why because it has gone through the process of normalization right it's interesting right you can apply different methods there as you do your reverse engineering depending on the environment that you are in and so then finally I'd like to show you how you can apply reverse engineering to an instance right so let's say that I have a mongodb instance that I want to reverse engineer from well I've got a connection here pre-configured to an instance in mongodb Atlas right and I'm going to connect to that instance and say well these this is the database and these are the collections that I would like you to reverse engineer for me right so there's movies comments sessions theaters users in there now there's a really interesting capability here that is specific to the mongodb environment which is that it will allow me to attempt in for inferencing the relationships between collections based on object IDs what does that mean you know in every collection you will have documents obviously and those documents will have IDs object IDs if two collections have corresponding object IDs and that means that we can infer that there is a relationship between those two entities and like you see here right so we have a movies collection right and that has a particular structure right we also have a comments collection that also has a particular structure and that relationship is there because the movie ID here corresponds to the movie ID over there great so with that I I think I've shown you uh some of the possibilities of our reverse engineering tool set and um obviously there's much more to show there I invite you to continue to read up on our documentation the blog and of course the Fantastic new book on mongodb database modeling and schema design look forward to working with you on this in the future if you have any questions please reach out and if not I will wish you a fantastic rest of your day bye