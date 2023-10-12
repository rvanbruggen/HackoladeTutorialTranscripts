
# Tutorial 2 - Intermediate part 2 - Add choice, conditional, pattern fields

[URL of video: Tutorial 2 - Intermediate part 2 - Add choice, conditional, pattern fields](https://community.hackolade.com/slides/slide/part-6-add-choice-conditional-pattern-fields-13?fullscreen=1)

## Unedited transcript of the video

hello everyone and welcome to part six of our Hackley tutorial for the past two parts of the tutorial we've been creating our data models right um first a simple data model in part four and then we were starting to create nested objects and arrays in part five and now in part six we're going to take it one step further and add Advanced Data types to our data models uh Advanced Data types like Choice conditional or pattern Fields I should however say that this is a technology and these are data models that are specific to Json schema based data models right choices conditional and pattern fields are Json schema based capabilities that are not going to be available in all target Technologies it's really limited to the technologies that use the Json schema capability if it's not available in your target technology then obviously the feature will be disabled so let's start we'll start with the choices right that's the first type of field that you can add to your Json schema it's a really interesting one because it allows you to combine schemas together right you can basically say you know I'm going to have a field here whose value will be validated against multiple criteria right choice criteria when you do that you can also combine this with a hackley's referencing technology right which allows you to pull in information from other models or other other objects that you have stored in your library and thereby combining schemas assembling schemas from multiple files depending on the choice that is made so therefore this is actually a great way to implement something we call polymorphism the capability of a Json document to take multiple shapes it's a great way to deal with changing requirements and evolving and flexible schemas both at the document structure level and also at the field level you can implement this at a variety of different levels you know thanks to the nested nature of these types of documents so one great example is that a field in your document can either be a string or a complex sub schema we'll go into that a little bit later on that way you can combine the schema of multiple documents into your particular environment the choices that you have as part of Json schema are one of the four that you see here on the screen right so all of or it's basically an and condition means that the constraint must be valid against all of the sub schemas any of means that this constraint must be valid against any of the sub schemas or one of means that exactly one of the sub schemas must be valid xor and not obviously means that the constraint must not be valid against the sub schemas a great example and we'll go into that in the short demo after this is an example of polymorphism is a shipping address right you've probably seen this yourself in many shopping cart applications where you can either say okay my shipping address is equal to my billing address or it is a separate address and that's exactly what you see here right so you have a a document that is representing a person right and first name last name that person has an address a billing address right which is street name house number city and state and then here you have a choice field where you can see that the the um the individual in this document can either have a string that is selected as the shipping address which basically means it's identical to the billing address or you can say it's actually a completely separate address right where is it completely separate street name house number city and state right so that's the way that you can do this and before we continue I will actually take some time now to show you how this is done right how you can implement this in the Accolade studio and so we're going to switch to that part of this tutorial right now all right so let's show this I've got my little model right here where I have a document that has a first name and a last name already set up it also has an address document in there already what I'm going to do now is I'm going to basically expand this because I've already got a billing address pre-configured here and I've got it converted into an internal definition as well so that I can easily reuse it and I'm going to now say okay I'm going to have a choice capability for a shipping address to be added to this document based on the choice of the user right so it's in both cases it's going to be a shipping address but in this case it's going to be a string right it's going to be a string that is going to basically say okay this is my shipping address and in the other case it's actually going to be something completely different which is it's going to be a full-on address right it's going to be an address that I'm going to choose from an internal reference here right so now I have a completely separate structure that I've added here based on the um internal definition so as you can see here now I've got the two options right either the billing address and the shipping address are the same that will be indicated in this string over here or the billing address and the shipping address will be separate and they will be of the same structure it will be completely similar structures that are now also defined in my Json schema great with that we're going to return to our presentation and continue with the next specific case which are conditional fields conditional fields are interesting because they allow for the application of a sub schema depending on the outcome of another schema right they're also interesting because they've also been misapplied quite a few times they are not intended to be used for multiple data types as part of your Json documents it's a very different application multiple data types can also be implemented but using different parts of the specification the conditionals are really these if then else statements that you can specify you know what has to happen if certain conditions are met or not met a great example of this is for example choosing the format of a postal code right so every country has its own different way of formatting the postal codes and depending on the value that we find in the country field we would apply a different format to the postal code field that is also part of this document so it's really easy to apply this in Accolade and we will show you that in a minute so let's switch right over and show you that immediately so here we go we've got a little demo document right here which is going to illustrate my conditionals I have a country string right here a field that is a country string I have a street address here that is also a string and now what I'm going to do is I'm going to have a new attribute which is going to be a conditional attribute based on the value of the country right so if the country has a constant that is equal to USA then the postal code right is going to have a particular pattern right which I'm going to copy in right now right and that pattern is going to be equal to this right if it's not the country equal to USA then I might have a different type of postal code which I'm going to paste in over here as well right and that's this pattern over here and I have this name here as well so you see this is how you can Implement these conditionals really really easily thanks to the visual Json editing capabilities of Accolade you can obviously also immediately see that in the preview here right so there is an if statement here then else I know all of that is very very easily accessible right in the Accolade Studio so with that we're going to switch to the last part of our tutorial here which is all about pattern fields so let's talk about pattern Fields pattern Fields function in exactly the same way as standard Fields do but there's a little bit of an exception the name in the name value pair is not a fixed string but it's actually a regex pattern right as you can see it over here on the screen right so the followers that you find here in the pattern example right abc123 and ABC 789 you know these are actually variables that you will be able to use in the pattern field right so pattern fields are typically controlled by a regular expression right so that's why it's called a pattern field and you shouldn't look at it as a field name but rather look at it as a key to a sub-document when embedding something in that document right it lets you easily access access the write sub-document inside an array or a main document using the dot notation right so this is the way how you can do that right and I'll quickly go over some of the mechanisms that you have inside hacker days to efficiently add these structures to your Json document let's go there so here we have our little document right the pattern example with the followers in there right and what I'm going to do now is I'm going to go into the schema of that um of those followers and I'm going to add a pattern field right I'm going to add a pattern field that is a document right and that document is going to be composed of a field that has a string the name right but it also is going to have an array right over here right and that array is going to be the sports of the those followers right so now we have the structure that we wanted right so we have followers that can are accessed with this regex based identifier then you have the name and then you have an array with the string just like we had it specified in our example over here so with that I'm going to wrap up our sixth part of the Hackley tutorial I invite you to look at some of these reading materials that you see here on the screen I hope they are useful for you and then you can obviously also refer back to some of the questions that you find as part of the tutorial as well and hopefully that will be useful for you I wish you a wonderful rest of your day