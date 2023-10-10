
# Tutorial 4 - Expert part 20 - Compare and merge

[Tutorial 4 - Expert part 20 - Compare and merge](https://community.hackolade.com/slides/slide/compare-and-merge-27?fullscreen=1)

## Transcript of the video

hello everyone and welcome to today's highlight tutorial in this episode of the Accolade tutorial we'll be talking about how you can use the Accolade Studio to compare and repair and merge different data models this is an important piece right because hackerlade promotes the usage of git for powerful and flexible model versioning right we don't have our own repository for this we don't have our own system for this we literally just leverage something that is proven and very very powerful and flexible which is the git based system this allows us to have people collaborating on the model in parallel right so that you can have versions of the data models evolve in parallel side by side right without blocking each other without having this check-in checkout based lock system where some people wouldn't be able to do any modifications on a Model while someone else does right git is much more advanced in that way because it allows allows us to facilitate different versions and merging them together as required it also helps us um to for example uh have additional governance processes on our productional systems right so for example one thing that people use to compare and merge functionality for is um to inspect a production system automatically using the Highlight command line interface and comparing that derived or reverse engineered version of the model automatically with a previous version of the model that has been documented and validated right so if those two versions of the model are not consistent or not the same then obviously we have a governance procedure that needs to be triggered to make sure that we understand why that would be the case comparison and merger processes the subject can be different right so you can have a previous version of the reference model be the comparison the subject of the comparison or the merger it could also be something that you reverse engineered like I was just explaining you know for governance purposes or it could be something that has been evolving and get in separate branches for example in the uh Hackley tool set you will find that there's two distinct views there's a comparison view with two two pane side by side and there's a merger view where those two panes will be complemented with a new middle pane that suggests a resulting merged model you can access this functionality from the welcome page or from the tools and then the first thing that you will be asked to do is to select the left and the right model that you want to be comparing you can solve these easily but the order of left and right is of course important because it will have an impact on what the difference actually means between those two versions of the model the comparison screen will offer you synchronized scrolling capabilities and the convention will be that the left hand model is the basis right and so if the left hand model contain contains fewer attributes than the right hand model then that will be in addition right there's something being added to the model if the left hand model contains more Properties or objects than the right hand model then that means that there's a removal or a deletion right the comparison screen will also identify moves you know where things are positioned in the model and modifications to the properties of objects obviously let's take a look at how that looks so here you've got the comparison screen right with the two panes and all the different differences are highlighted appropriately and then you will also have the possibility to generate a Delta model a Delta model is a formalization of the differences between the two versions of the model it basically lists that in a structured way and importantly a Delta model can be the basis for what is called an alter script right that's an alterscript is basically the schema instructions that you will fire at or run execute on the target instances to go from one version of the model to the next version of the model right so it's altering the schema of that instance right so let's take a look at that we'll switch to the Accolade Studio here just to illustrate the comparison functionality I have a couple of models here right so I'll open them from my downloads folder here right so this is a mongodb model that I have over here and in that mongodb model I have made one change I've added a property over here right so there's a score one that has been added this is V1 of the model in VT V2 of the model you will see that there's another property that has been added here score two right and so what I'd like to do now is I'd like to compare those two versions of the model so I'm going to go into my downloads folder and I will be opening the V1 on the left hand side and V2 on the right hand side I can switch this easily using the Double Arrow over here now I should quickly add here that these two models always have to be of the same type you have to compare a mongodb model with a mongodb model you cannot compare a mongodb model with a postgres model for example right and then it was going to tell me okay what is the difference between here you can see the synchronized scrolling at work score one is on the left inside score 2 is on the right hand side but it's positioned at the same level because I'm matching on the internal IDs what I've done here is I've copied the model and I've modified it but if I would match it on the business name then you will see that it does a different type of comparison it's basically saying well this one's been removed and the other one has been added right so this is uh how you can have different variations of that comparison and you obviously want to know exactly how that is done when I push the generate Delta model I'll just open that up here for you because I've already prepared that over here you will see what the Delta is right so this is the Delta model which is basically a formalization of the differences between the two versions right where this one has been added and this one has been deleted right the script however the mongodb script doesn't give me like these alteration commands or anything like that because mongodb doesn't allow for that which is why I'd like to show you a different version of this compare person right so I'll go back into my downloads folder and I'll show you the postgres version right so there's a postgres version here that has a new property over there and then there's another postgres version over here that has a different property oh yeah over there in the film table over there right so if I now generate the compare those two right I'll get something very very similar but you will if I come if I then open the Delta model right between those two postgres models you will see that it actually gives me an altar script in the autoscript you will have the addition of the column and the dropping of the column right but the dropping of the column because that's a you know potentially dangerous operation is commented out right so with that I hope you have a good example of what the model comparison is like and we'll switch back to our presentation here to go into how you can merge models together right so how are you going to do that well so very similarly we're going to take two models right and we're going to be comparing those two right but there will be a third new pane that you will see in a minute here that is going to give me a merge proposal right and I can select and unselect those proposals and if there's any conflicts then the merge proposal is going to use the right hand model value right and deletions are also going to be retained unless unchecked right so the merging is done in this three pane uh view here so so now I'm going to uh open up those two models again right so V1 on the left hand side and V2 on the right hand side and the comparison screen will show up but at the top here I can toggle and say well why don't we go into a merge uh scenario here and then you know again if I switch to the different merging uh or matching strategies here it will give me different results right so and now it's going to tell me okay you can actually save this new model right in a merge model right and that model can then be opened up and you will see that there is a um a new version of the model that I can show you in a second here and that new version of the model will have both of those properties um in the entity over here score one and score two as you can tell great so with that I'm going to wrap up this tutorial and show you a couple of reading materials obviously these are always interesting and important but I would highly recommend that you take a look at these and with that I'm going to wrap up this tutorial and wish you a very good rest of your day thank you very much