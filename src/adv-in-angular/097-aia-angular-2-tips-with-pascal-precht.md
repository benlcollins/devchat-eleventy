---
layout: layouts/post.njk
title: >
  097 AiA Angular 2 Tips with Pascal Precht
date: 2016-06-16 07:00:13
episode_number: 097
duration: 47:53
audio_url: https://media.devchat.tv/adventures-in-angular/AiA097PascalPrecht.mp3
podcast: adv-in-angular
tags:
  - adv_in_angular
  - podcast
---

## Get your early bird tickets for [Angular Remote Conf](https://allremoteconfs.com/angular-2016)!

&nbsp;02:13 - Pascal Precht Introduction

- [Twitter](https://twitter.com/PascalPrecht)
- [GitHub](https://github.com/PascalPrecht)
- [Blog](https://pascalprecht.github.io/)
  04:29 - [ng-conf](https://www.ng-conf.org/)
- [Angular-upgrade-demo](https://github.com/thoughtram/angular-upgrade-demo)
  06:42 - Dependency Injection; [@Injectable](https://angular.io/docs/ts/latest/api/core/Injectable-decorator.html)
- emitDecoratorMetadata
  12:51 - Component Interaction and Communication21:35 - [ContentChildren](https://angular.io/docs/ts/latest/api/core/index/ContentChildren-var.html) and [ContentChild](https://angular.io/docs/ts/latest/api/core/ContentChild-var.html)23:34 - [ViewChildren](https://angular.io/docs/js/latest/api/core/ViewChildren-var.html) and [ViewChild](https://angular.io/docs/ts/latest/api/core/ViewChild-var.html)24:31 - Change Detection
- [Pascal Precht: Angular 2 Change Detection Explained](https://blog.thoughtram.io/angular/2016/02/22/angular-2-change-detection-explained.html)
  &nbsp;Picks
- [Professional Ado Rds Programming With Asp](https://www.amazon.com/Professional-Ado-Rds-Programming-Asp/dp/1861001649) (Lukas)
- [Data-Driven Services with Silverlight 2 by John Papa](https://www.amazon.com/Data-Driven-Services-Silverlight-John-Papa/dp/0596523092/ref=sr_1_3?s=books&ie=UTF8&qid=1464214393&sr=1-3) (Ward)
- [ZEIT](https://zeit.co/) (Joe)
- [Overwatch](https://playoverwatch.com/) (Joe)
- [5thingsAngular](https://5thingsangular.github.io/) (Pascal)
- [Dr Pepper](https://www.drpepper.com/) (Pascal)
- [NOMAD](https://www.hellonomad.com/) (John)
- [Gilderoy Lockhart](https://harrypotter.wikia.com/wiki/Gilderoy_Lockhart) (John)
- [RIF6 Cube 2-inch Mobile Projector](https://www.amazon.com/RIF6-Projector-120-inch-Portable-Rechargeable/dp/B00QXS8L6I?ie=UTF8&psc=1&redirect=true&ref_=oh_aui_detailpage_o00_s00) (Chuck)
- [Fully Alive: Lighten Up and Live - A Journey that Will Change Your Life by Ken Davis](https://www.amazon.com/Fully-Alive-Lighten-Journey-Change/dp/0849948428?ie=UTF8&keywords=fully%20alive&qid=1465489342&ref_=sr_1_3&s=boost&sr=8-3&srs=12034488011) (Chuck)

### Transcript

**WARD:&nbsp;** Alright [Huck], you too can pretend to know Angular 2.

**JOE:&nbsp;** [Laughs] In 10 easy steps…

**WARD:&nbsp;** [Laughs] That's right. One, listen to our show. [Laughs]

**JOE:&nbsp;** Two, say these words over and over again.

**LUKAS:&nbsp;** Repeat after me.

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the Adventures in Angular link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/AdventuresInAngular.]_**

**_[Ready to master Angular? Oasis Digital offers Angular Boot Camp, a three-day, in-person workshop class for individuals or teams. Bring us to your site or send developers to ours classes in St. Louis or San Francisco – AngularBootCamp.com.]_**

**_[This episode is sponsored by Telerik, the makers of Kendo UI. Kendo UI integrates seamlessly with both AngularJS 1.x and 2.0. It provides everything you need to integrate with AngularJS out-of-the-box bindings, component configuration, directives, template directives, form validation, event handlers and much more and yet Kendo UI tooling does not depend on AngularJS. So, if you want to use it with Angular or not that’s totally up to you. You can check it out at KendoUI.com]_**

**CHUCK:&nbsp;** Hey everybody and welcome to episode 97 of the Adventures in Angular Show. This week on our panel we have Ward Bell.

**WARD:&nbsp;** Hi everyone.

**CHUCK:&nbsp;** Joe Eames.

**JOE:&nbsp;** Hey everybody.

**CHUCK:&nbsp;** Lukas Reubbelke.

**LUKAS:&nbsp;** Yo **.**

**CHUCK:** &nbsp; John Papa.

**JOHN:&nbsp;** Hello.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. It's a little ways out but start looking forward to Angular Remote Conf. We have a special guest this week and that's Pascal Precht.

**PASCAL:&nbsp;** Hello.

**CHUCK:&nbsp;** We haven't had you on for a little while, Pascal. Do you want to introduce yourself?

**PASCAL:&nbsp;** Oh yeah, sure. So, my name is Pascal. I'm from Hanover, Germany. I'm a software engineer and trainer and I like to do Angular.

**WARD:&nbsp;** You're also a Git trainer too, right?

**PASCAL:&nbsp;** I also do Git, yeah. That's correct. But more Angular. [Chuckles]

**WARD:&nbsp;** I've learned almost, most of the Git that I needed I learned from you I'll just say that.

**PASCAL:&nbsp;** I'm happy to hear that.

**WARD:&nbsp;** Well, you wouldn't be so happy if you realized how terrible I am at Git. But that's…

**PASCAL:&nbsp;** [Chuckles]

**WARD:&nbsp;** I'm just kidding. Okay. So, you're based in Germany, right?

**PASCAL:&nbsp;** That's true.

**WARD:&nbsp;** But you and your partner, Christoph…

**PASCAL:&nbsp;** Christoph, Christoph Burgdorf. He's awesome. He's my… actually, so today, no this week, I learned a new word. It's called protégé. And I think I'm Christoph's protégé.

**WARD:&nbsp;** Ah.

**PASCAL:&nbsp;** Does that make sense?

**WARD:&nbsp;** It does. And the two of you are in the workshop business, right?

**PASCAL:** That's right, yeah.

**WARD:&nbsp;** And you're hopscotching around Europe mostly, giving classes?

**PASCAL:&nbsp;** Right. So basically, we're doing in-house training, some public training, and we basically do it all around the globe. So, we're mainly doing it in Europe. We also do it in the US but mainly Europe currently. And so yeah, we like to travel so we travel around. We visit cities and do our trainings there, meet great people, work with them, and yeah, that's what we do.

**JOE:&nbsp;** So, I've got a question for you. Doing Angular in Germany, is it a lot more efficient there?

**PASCAL:&nbsp;** Efficient in what sense?

**JOE:&nbsp;** It's a joke.

**PASCAL:&nbsp;** Oh.

**JOE:** Nobody laughed.

**CHUCK:&nbsp;** [Laughs]

**JOE:&nbsp;** Come on.

**WARD:&nbsp;** It was just one of those “I don't believe it” kind of jokes. I can't…

[Laughter]

**WARD:&nbsp;** [Sighs] Yes.

**PASCAL:&nbsp;** So actually…

**JOE:&nbsp;** German cars are known for being very efficient.

**PASCAL:&nbsp;** [Chuckles]

**JOE:&nbsp;** And well-engineered. Is Angular better engineered in Germany?

**PASCAL:&nbsp;** Yeah, I'm pretty sure. That's also…

**JOE:&nbsp;** I think the engineering is better.

**PASCAL:&nbsp;** That's also why all the tests are green when you write Angular.

**WARD:&nbsp;** In German. [Laughs]

[Chuckles]

**JOHN:&nbsp;** Wait, wait. Let's redo the question. Joe, ask the question again. This time we'll laugh.

[Laughter]

**JOE:&nbsp;** Forget it. Here's a pity laugh. It's only a dollar. You can have a pity laugh for a buck.

**WARD:&nbsp;** Yeah, exactly. Getting back on track…

**JOE:&nbsp;** Yeah, I want to talk about ng-conf, [them at] ng-conf.

**WARD:&nbsp;** Oh, go for it.

**JOE:&nbsp;** You guys were at ng-conf. You did a bunch of stuff there, right? Can you talk about that?

**PASCAL:&nbsp;** Yeah, sure. So, at ng-conf we've done a full day of training on Angular 2. So, we basically recreated an Angular 2 application with a group of people that demonstrates what is needed to build a basic application, what you need to actually get started, to have something that works. And then from there, you can move on and extend that application. We've used some tools for that. There's the Angular CLI tool for example that is, it's pretty much a first-class citizen in our training materials. So, everyone learned how to use the Angular CLI which is pretty cool because it takes away all the hassle of setting up a new project. Because in the current world of JavaScript and tooling you have to learn tons of stuff to actually get started, which is quite cumbersome. I'm actually, I haven't even used Webpack myself. I never set it up myself. So, I'm super happy that there's something like Angular CLI that also handles things like SystemJS and the whole module thing and transpiling TypeScript code. And so, we did that.

And then we've done a one-hour, it was a kind of talk but at the same time also showcase how to upgrade an Angular 1 application to Angular 2. So, there's this module out there called ngUpgrade and it provides APIs to upgrade an Angular 1 application to Angular 2. It has APIs to upgrade and downgrade components and services, providers and that kind of stuff. And so, what we did was we basically, we took the application that we created in the Angular 2 training. We had the exact same application built in Angular 1 and then we used ngUpgrade to demonstrate how we can upgrade that application to Angular 2. actually, there's a repository out there on GitHub which has all the steps in a nice commit history so you can actually go there and then take a look at it and see how that worked. That's what we did.

**WARD:&nbsp;** Let's put that in the show notes.

**JOE:&nbsp;** [Yeah, really].

**WARD:&nbsp;** So, you're known for these wonderful little tip posts on your blog. And that got us to thinking that it would be great to pick your brain on the kinds of tips that you think Angular 2 developers should know about. And I assume you're game for that. Let's pick one. Can you talk to us a little bit about dependency injection? In particular, that peculiar decorator called @Injectable.

**PASCAL:&nbsp;** [Chuckles] Of course, yeah. So, @Injectable is a funny thing. If you go to Angular.io, if you take a look at the official documentation which everyone out there definitely should do because there are tons of good material there to learn Angular 2, you'll see that in many examples where you have service code you will see that the service class has an @Injectable decorator. And you will see it pretty much on every service class. So, that kind of brings up the feeling that whenever we create a service in Angular 2 that we want to inject somewhere we need to add this @Injectable decorator. And in fact, we also like to promote that as a best practice, to add the @Injectable decorator to every service that we create because it turns out that actually it's not needed in every case. It's really, there are some cases where it's required to add this decorator. But it's not a big deal if we add it on every service class. And I can explain [real quick] what it's all about.

So, the thing is that when we write TypeScript we have these decorators as a language feature available. And these decorators are basically used to create metadata on our code. So, it's basically information that Angular 2 uses to do some certain things. And dependency injection is one of these parts of Angular 2 that take advantage of metadata. So, whenever we use for example type annotations in our constructors to inject stuff, that's also metadata that the DI system needs to find out what to actually inject. And so, the problem with [simple] service classes is that if you have a class and it doesn't have any decorators on it and it also doesn't have any dependencies then it's alright. You can just simple create an object of that class and you can inject it and you're ready to go. But as soon as your service has its own dependencies, let's say you have a data service and it asks for an instance of something of type HTTP, then at that particular point we need to make sure that TypeScript actually generates metadata for that class.

And there is one mechanism that generates metadata in TypeScript and that is a decorator. So first of all, there is a configuration option. I think it's called 'emit metadata' or something. That needs to be set to true to tell TypeScript “Hey, please generate metadata in general if you need to.” And the question is when do we have the case that TypeScript generates metadata? And that is only when there is a decorator on a class. So, if there's no decorator on a class then there is no metadata generated for that class, which means if you have a dependency defined in your data service and that class doesn't have a decorator, then there is no metadata generated. And that means at runtime the DI system doesn't know what it needs to inject. And so, that's why you want to add some sort of decorator. You can basically add any decorator but it happens that there is already a decorator flying around called injectable. And that decorator is part of Angular 2 because it's actually required in Dart. And so, we basically just use that decorator as it's already there to take advantage of that.

**WARD:&nbsp;** So, it's just a marker that triggers the TypeScript compiler to emit the metadata, is that the idea?

**PASCAL:&nbsp;** That's correct. And so, we don't have to do this when we create components. You might wonder, why don't we have to do this when we create a component class? Because there we inject stuff too, right? Well, the thing is that a component already has [a decorator], the component decorator. So, there is already a decorator. That's why you will never run into this when you create a component. Whereas a service can be just a simple class. It doesn't need a decorator to be a class.

**WARD:&nbsp;** Okay, so let me see if I got this. So, if I want to have a component, let's say it's a hero list component that's going to display a list of heroes, in order to do that it needs a hero service. I don't need to add @Injectable on there because I already did what with my hero list component?

**PASCAL:&nbsp;** Well, because in order to make it an actual component you add the @Component decorator to your component class.

**WARD:&nbsp;** Ah, I see. So, that decorator, any decorator, will do the job?

**PASCAL:&nbsp;** Correct. Any decorator will tell TypeScript “Hey, please generate metadata for this class.” So, you could actually, technically you can actually go ahead and create some custom decorator. You can call it foo and then you put the @foo decorator on your service class and that would work the same way. You just don't want to do it because there is already a decorator that you can hijack for that use case. On the other hand…

**WARD:&nbsp;** That makes…

**PASCAL:&nbsp;** Sorry, as I mentioned earlier, it's actually considered a best practice to just simply always add the @Injectable decorator to a service class because it's a kind of, it's a positive negative. It will generate the metadata for that class even though it's not needed. But you don't have code that breaks.

**WARD:&nbsp;** Well, and I don't want to sit around and say “Do I need it this time? Do I not need it the next time?” Hey, if I just throw it on there, done. And I can stop thinking about it.

**PASCAL:&nbsp;** Correct. In fact, Angular CLI does that also by default. Whenever you scaffold an application in Angular CLI and when you create a service using, you have a generator command for that. So, in your command line you say 'ng generate service' and then you give it a service name, what Angular CLI does is it creates a service for you. It creates a spec file for you so you don't have to set up all the testing environment. And the class itself, the service class that is generated, already has the @Injectable decorator on it.

**WARD:&nbsp;** That's neat. So, let me ask you about another set of things. The mystery decorators. This is sort of a general problem of I got two components or a component and a directive and I want them to… I want to know how they interact with each other. And if I've got a component and it's got components inside it, how does that outer component know about the inner components? And there seems to be a whole bunch of decorators dedicated to that. But can you tell people about that?

**PASCAL:&nbsp;** Yeah, sure. So basically, I think if I'm getting you right you're basically talking about a directive or component communication, right?

**WARD:&nbsp;** Yeah. And just…

**PASCAL:&nbsp;** Like how do you access instances of for example child components in a parent component or maybe even the other way around?

**WARD:&nbsp;** Exactly, exactly.

**PASCAL:&nbsp;** Yeah.

**WARD:&nbsp;** And I keep seeing these decorators floating around that seem to have something to do with it. But maybe you can tell us about them.

**PASCAL:&nbsp;** Yeah, so basically there are three different ways to do that. And two different directions. So, there's one use case where you might want to get an instance of a parent component in a child component. So, if you think for example, if you think about a tabs component. So, you have a tabs component to generate a tab group. And inside that tabs component you have many tab components.

**WARD:&nbsp;** Mm.

**PASCAL:&nbsp;** So, in order to create this tabs group you want the tabs component to generate a list of tabs. And in order to make that possible you somehow need to make sure that this tabs component knows about its child components. And so, one way to do it is basically to tell the child component, the tab component, “Hey, get an instance of your parent tabs component and then add yourself to that tabs list.” So, that's basically a child component requesting a parent component. And you can simply do that by dependency injection. It's a nice thing. They dependency injection system in Angular 2 is, it unifies the different use cases and implementations that we had in Angular 1 where you would have dependency injection for services and filters and directives and stuff. And then you have in directive objects, you have this link function where it can access parent controllers. And in Angular 2 you simply have this one single DI mechanism for that. So, you can simply ask for the parent component using type annotations like the way you're used to it. And you will just get an instance of your parent component. That's one way.

But doing that basically means that the child component, the tab component is now actually coupled to the tabs component. In this particular case it might even make sense because you probably don't even want to use the tab component alone. But there might be use cases where you say I actually don't want my child component [to] know about the parent component at all. But still, there needs to be some sort of connection. Somehow the parent component needs to deal with the child components. And when you're in this case, actually you can also do that with this tabs example, you have a couple of decorators that you can use to get hold of your child components.

So, there are four decorators that you can use for that. There's the ViewChild decorator. There is the ViewChildren decorator. And then there's the ContentChild decorator and the ContentChildren decorator. So, we have singular and plural. And so basically, what they do is they allow you to basically say “Hey, I have my tabs component and I want to get all of the children tab components that are in my content.” The content is basically the HTML that is inside the component's tag. So, it's not the view of the component, not the template of the component. It's the HTML that is basically between the tags of that component. So then, what we could do is we could basically use the @ContentChildren decorator. We give it the tab component type that we have because we created a component for it. And it will automatically asynchronously basically get a list of all the available child components that we requested.

And the cool thing about that is that it is all based on observables. So, you basically get a stream of changes that are happening to a query list, a so-called query list. So, what you get from ContentChildren decorator is a query list that gets a stream of children components. So, that's a pretty cool way to actually get a hold of child components without the child component knowing about the parent component. And basically, you can do the exact same thing if you want to address child components in a components view. So, if you have a template of a component and if you want to access…

**WARD:&nbsp;** Well, let's… hold a second there, Pascal, because I want to make sure we can draw…

**PASCAL:&nbsp;** Oh, sorry.

**WARD:&nbsp;** Draw the picture of what you were doing. So, let me see if I got this right. So, if I have a tab container that holds tabs, that's the example, so you're saying that I might… and let's suppose that there was a tag, we created an element called tab container, that I would go tab container, then I would have a bunch of these tab or tab panes inside it. And then I would have a closing tag that said tag container. So, the component behind the tab container, that's the thing that's going to get ContentChildren, right?

**PASCAL:&nbsp;** Correct. If you want to get…

**WARD:&nbsp;** And all those little tab elements that I put in the middle that represented the first, second, and third tab, that's the content?

**PASCAL:&nbsp;** Right. That's what you get when you ask for the ContentChildren.

**WARD:&nbsp;** Got it.

**PASCAL:&nbsp;** Right.

**WARD:&nbsp;** Angular 1 people might have known that as transclusion, wouldn't they?

**PASCAL:** Not exactly, because…

**WARD:** Did I just blow the whole thing [inaudible]? [Laughs] Forget about transclusion.

**PASCAL:&nbsp;** So transclusion, you really take everything and put it somewhere in the view of the component. Whereas with ContentChildren you don't put anything into the view yet if you don't want to. So, it's actually a different mechanism. In Angular 2 that's content projection and that would work pretty much the same way. But that's a different thing. So yeah, that's ContentChildren or ContentChild depending on what you want to do. But then if you…

**WARD:&nbsp;** And that has to be observable, right? Because [inaudible] tabs, so I could have three in the middle?

**PASCAL:&nbsp;** Yeah.

**WARD:** Okay. So, that's why you need to listen to this for changes to that because that could be happening outside. You wouldn't know.

**PASCAL:** &nbsp; Correct, yeah. Right. Or you can even, like when you… yeah you might even generate those child components dynamically using ngFor or whatever. And then maybe those components are created using some asynchronous data call or whatever. So, maybe the data that you used to create these components is already asynchronous. So then, you need to have a way to asynchronously get a hold of these components.

**JOHN:&nbsp;** Pascal, why would you want to get a hold of these components? I want to make sure we make that clear to folks.

**PASCAL:&nbsp;** Well, so in the case of this tabs component specifically, if you want to create an actual list of tabs that you can click on, the tab container needs to know about all the available tabs in order to create that list. So, you need a way to access these children. And that's why you would ask for the content children in that case.

**WARD:&nbsp;** You mean like the labels on the tabs themselves might be controlled outside of them and they'd have to get the value or something like that? That might be an example?

**PASCAL:&nbsp;** Well, so the general generation of that list. So, basically what you generate… so you write your HTML. You have the tabs container and the tabs tags. And what you, actually what you want to generate is a list an HTML list with all the tab labels and then a div container where the content is projected for each tab. So, in order to create this list, this list is dynamic, we put that together based on the available tab components. The tab container needs to know about its children. Otherwise it cannot generate that list. So yeah, that's why you want to use the ContentChildren decorator. It's really just a way to access that data, these components, without the child component knowing about the parent.

**JOHN:&nbsp;** So in your scenario, are you generating the tabs form the tab container or are you accessing them?

**PASCAL:&nbsp;** You're generating the tab group in the tab container based on the tab children.

**WARD:&nbsp;** Well, I guess it could be either. The tab container might be responsible for populating them or it's something outside, elsewhere could be responsible for generating them. The point is that the tab container needs to interact with the little tabs that are inside it and it needs a mechanism for getting a hold of those things and communicating to them. And that's what you're saying.

**PASCAL:&nbsp;** Yeah.

**WARD:&nbsp;** Getting the content children lets you do.

**PASCAL:&nbsp;** Yeah. That really is what I'm trying to say. But probably I'm not very good at it. [Chuckles]

**WARD:&nbsp;** We have to say things six different ways before any of us understand it.

**JOHN:&nbsp;** So, there's ContentChildren and there's ContentChild.

**PASCAL:&nbsp;** Yes. So, ContentChild is as you might guess the singular version of it. So, if you know that you're only interested in one component instance of something then you can just use the ContentChild.

**JOHN:&nbsp;** What if you don't know? Should you just use children and deal with it?

**PASCAL:&nbsp;** That's a good question. I would probably, oh actually, I don't have an answer for that. [Chuckles]

**JOHN:&nbsp;** Oops. Sorry.

**PASCAL:&nbsp;** It's alright.

**WARD:&nbsp;** Oops. I have an answer. When you say ContentChild you're going to get the first one if there's more than one. So, the equivalent is to query for the children and ask for the 0<sup>th</sup> element. So, I guess you have to know something about whether you're expecting a collection or not. But if you're only interested in the first one, then go for it. So, ContentChild and ViewChild are simply, they're sugar for saying look at the list and pick the first one.

**PASCAL:&nbsp;** Then I think it just…

**JOHN:&nbsp;** So, that makes me wonder though. Could we not just use ContentChildren and always look at the array length and then see, and then use that?

**PASCAL:&nbsp;** This is just a guess. I think there's like a performance penalty. And also that might affect how the offline template compilation would work. I think it's better when we're…

**JOHN:&nbsp;** I think you're right. I remember a conversation where the Angular team was talking about this. And WPF folks had a similar scenario where you have, if you don't know if you have multiple children or one you can actually have a performance impact if you just know “Look, there's only one. Let me go get that one.”

**PASCAL:&nbsp;** Yeah.

**JOHN:&nbsp;** I think that's actually more performant. But we're guessing

**WARD:&nbsp;** Well, I'm going to guess…

**JOHN:&nbsp; We're** guessing. [Laughs]

**WARD:&nbsp;** I'm guessing the opposite. But because you do get in a life cycle hook event that tells you when it changes, it's [inaudible]

**JOHN:&nbsp;** That could be a challenge. We have to find out.

**WARD:&nbsp;** Yeah, we got a challenge. We got a code challenge. But it's a practical matter, I'm either expecting one or I'm expecting many. So, I would write whichever seemed to fit my pattern, my expectation.

**JOHN:&nbsp;** Yeah, that makes sense.

**WARD:&nbsp;** That's content. That's the stuff where you have an open and close tag and you're interested in the stuff between the tags. What is the difference between… that's the content stuff. What's the ViewChild?

**PASCAL:&nbsp;** Yeah, so the ViewChild and the ViewChildren is pretty much the same thing, just for the component's view. And the component's view is basically the template that you define for your component. So, instead of asking for components that are between the tags of your component you're actually asking for something that is already in the template, that is already there.

**WARD:&nbsp;** Is that like when I do an ngFor of heroes, that kind of thing? In my template.

**PASCAL:&nbsp;** Correct. Like when you have a list of heroes that you generate in your component you can… for each iterator you would actually generate a component, you would be able to access this view components using ViewChildren with the same mechanism, just that you're basically, you're asking the view and not the content.

**WARD:&nbsp;** Yeah, that makes sense. So, you've been exploring change detection in Angular 2.

**PASCAL:** Oh yeah, that's true.

**WARD:&nbsp;** And change detection in Angular 2 is a lot different than it is in Angular 1. So, maybe you could start with what is change detection. And then what are we used to in Angular 1 and how is it different in Angular 2? And then what are the options available to us?

**PASCAL:&nbsp;** Okay. Right, so that's going to be like a 45-minute talks. [Laughs] No, I'll try to keep myself short.

**JOE:&nbsp;** Ready, go.

**PASCAL:** [Chuckles] Alright. So, change detection in general is actually this simple idea of taking some sort of application state and then projecting that state to a visual UI to the user. So, that can be for example like a simple website. If you request a website, that website has some sort of data structures that it wants to represent at some point. And then you get a response and then you see the data in some way. And then but at some point there might be some [change], whatever, like you change some… you have a form or let's say you have a UI with… you see some data. You have a UI and you want to click a button that changes that data. And in a normal HTTP-based scenario you would send that form, you would click that button and then the server would do something and then you get a new response with that change. And so, this is basically what it's all about. You want to know when something has changed. And then if you know what has changed you want to update the view. And updating the view can be a complex task, depending on what your view is all about.

In the web world or specifically in single-page applications we have the DOM, the document object model that represents what we have written in HTML. It represents our templates. And so, the hard thing in the web world is basically making changes to the DOM efficiently because DOM operations are pretty expensive by default. So, what we want to do is when we build applications and there are changes happening where we want to project these changes in the view again, we want to keep these operations as low as possible. So, that's a general idea. And then there are different ways to deal with that. Like React has virtual DOM. I don't know what Ember has. But Angular had this thing called the digest cycle that synchronizes the model with the view. And Angular 2 has basically an improved version of what Angular 1 has done. Also actually, it's like a different mechanism.

And so, what Angular 2 does, so first of all we need to find out when a change happens. What does it mean? What does it change? So, in a change, in single-page applications, it's basically everything that is asynchronous. Whenever we have some asynchronous operation, changes could happen. So, if you have… if you think of this scenario, we display a name and that name is actually part of our model. And we click a button and say there's a function, an event handler, applied to that button that says “Hey, when you click that button then we change this name,” basically what happens is when this button is clicked application state could have changed. In fact, in this particular case it would. And so, what we need is a mechanism that tells Angular “Hey look, there was a change. So, please make sure that you update the view accordingly.”

And so, first of all to find out if there was a change or not Angular uses this feature called zones which is a language feature in Dart. And the Angular team backported it to JavaScript. Or actually, the latest version of Zone.js, is the library that they use, is written in TypeScript. And so, what Zone.js basically does is it's like a sort of execution context. So, you can take your application code, whatever it is, you just take your code, you can run it in a zone. And because you're running it in a zone you're able to hook into some certain events. A zone knows when it executes a task and also when it stops a task. And so, what it allows you to do is basically to execute a hook whenever a task [inaudible] or where a task has finished. And so, Angular basically listens for this zone. The zone fires an event.

It's also observable-based. So, it basically subscribes to an observable and it says “Hey, there is a task starting right now” and “Hey, this task is now finished.” So, this is your signal that you need to update the view because maybe something has changed. And so, what Angular does is it subscribes to that event. Whenever it fires it triggers a change detection. And then this is the moment where change detection itself comes into play. So, the mechanism of taking the application state and then representing that state in the view in a very efficient way.

And so, the change detection in Angular 2, without going into too much detail, there is this one key difference compared to Angular 1. It's that it always run from top to bottom. So, in Angular 2 we have a component tree and data always flows from top to bottom. So, we have data in a component. You pass it to a child component. That child component might also have children so it passes data to these children and so on and so forth. So, data can only come from top to bottom. And so, that's exactly the same way how the change detection mechanism works. So, it runs always from top to bottom. And it's not a cycle anymore. So, it's not that a model can update a model or a directive can update a model or a controller can update a model so that you have a cycle that is running over and over again until the model stabilizes. In Angular 2 you only have events, asynchronous operations that can trigger a change detection task. And so, that's the second thing that is different. There's no cycle. There's always just a single change detection task that is running. So, it only runs once for every component.

Although if you're in developer mode it runs twice to actually make sure that you don't create any side effects, which is pretty cool. And then…

**JOHN:&nbsp;** Pascal, let me digest this for a second. Get it, digest this?

[Laughter]

**JOHN:&nbsp;** Using a little Angular 1 [inaudible]

**CHUCK:&nbsp;** Watch it John, watch it.

**JOHN:&nbsp;** Ooh. [Laughs] So, I don't want to push too far, but we can take values from a component to the view and then from a view back to the component through one-way binding and then through event binding.

**PASCAL:&nbsp;** Correct.

**JOHN:&nbsp;** In Angular 2. So, we still get that two-way data binding. And as a general user first of all, do I really have to know how change detection works? Do I have to play with zones? Do I have to make any settings or make any changes or does it just work for me?

**PASCAL:&nbsp;** That should just work for you out of the box. So, you don't really have to know about zones and how zones work in order to build Angular 2 applications. But it's definitely helpful especially if you want to improve cases where even the Angular 2 change detection might be slow.

**JOHN:&nbsp;** So, that's what I want to focus on. So, I think I'm going to say 80%, just throwing out a number, 80% of scenarios I'm fine. I don't have to know about this. I can just use it.

**PASCAL:&nbsp;** Correct.

**JOHN:&nbsp;** What are those edge cases where, when is it time to say “Pascal, uh-oh. I need to go pull up your blog post on how change detection works because I've got a performance issue?”

**PASCAL:&nbsp;** Yeah, so for example if you have, say you have an application that is connected to a WebSocket server. And it sends data to your application many, many times a second. So, that would mean for every second you would get some WebSocket event. And zones automatically trigger change detection because they inform Angular about that event. So, that means every second due to this infinite WebSocket connection that keeps firing events, every second there would be a change detection task being executed. And it's probably something that you don't want. Maybe you just want to update your view only every five seconds or whatever, even though you get data every second. So in that case, you can actually control that flow and say “Hey, I want to run this only every five seconds. I'm only interested in running change detection every five seconds.” Or you can even disable change detection entirely and only reactivate it in some certain cases. So, in these kinds of cases you want to do that.

**JOHN:&nbsp;** Wicked awesome.

**WARD:&nbsp;** Would I do that with a zone? A special zone that you were talking about? Would I run that WebSocket in a separate zone so that Angular didn't hear it? What am I doing?

**PASCAL:&nbsp;** Well, let me think about it for a second. So, what you can do is, so there is one way. One thing you could do is you can actually execute code outside Angular. So, there's this API that says run outside Angular on the zones API. And so, what it allows you to do is basically execute tasks, execute code, even with asynchronous operations that will not inform Angular to run the change detection. And then if you combine that with something like setInterval or something you can basically make sure that it's only checking every five seconds.

**WARD:&nbsp;** That could be huge if you had a WebSocket or something like that, that was just firing stuff at you all the time that you couldn't eat fast enough.

**JOHN:&nbsp;** What if you don't have a WebSocket though? WebSockets are awesome. Don't get me wrong. But let's say I'm just building an app that's got no WebSockets. Is there any reason for me to play with these settings without WebSockets?

**PASCAL:&nbsp;** Why not? I'm playing with stuff all the time. [Laughs] So, I would say that in general, Angular 2 is pretty fast. Because it also, it generates monomorphic code on the fly for you. So, that is super-duper fast by default. So, if you… I think it's really hard to actually run into cases where this is not fast enough. But then if you really have cases where Angular is not fast enough, then this is the moment where I would start looking around what you can do, how you can improve the performance. Another thing you can do is actually reduce the amount of checks that Angular does. You can actually say “Hey look, I have this huge application. This big component tree. And I know that this subtree here will actually not change, for whatever reason.” And then you can tell Angular “Please don't check this subtree here.” So, it will skip the entire subtree which then again is way faster than checking all the components.

**JOHN:&nbsp;** That's awesome. And I'm going to put in the show notes here a couple of posts that you've written. One of them is the 'Angular 2 Change Detection Explained' where I think a lot of this stuff is made relatively clear with your examples. Specifically you've got a setting in here in the @Component decorator for change detection property to set the change detection strategy on push.

**PASCAL:&nbsp;** Correct. So, that's what it's for, right. So, it basically, it tells your component “Hey, only check this component if the following rules are true.” The first rule is any of the components and properties have changed. So, we know that data always flows from top to bottom. So, if you have a component that only depends on input properties then you can actually say “Hey, if nothing, none of these properties change, then you also don't have to check this component here because there is no change.” There is no reason to check the rest of the tree. And so, Angular basically does a reference check. If you combine that with immutable data structures you know when something has changed and when not. And you can let Angular know as well.

**JOHN:&nbsp;** Uh-oh, did you just mention immutability in front of Ward?

**PASCAL:&nbsp;** Is that a problem?

[Laughter]

**WARD:&nbsp;** That is a big problem.

[Laughter]

**PASCAL:&nbsp;** Okay. Well, at least…

**WARD:&nbsp;** [You stepped right] on a land mine there, buddy.

[Chuckles]

**CHUCK:&nbsp;** We've tried, but his opinion…

**JOHN:&nbsp;** [Inaudible]

**CHUCK:&nbsp;** We've tried, but his opinion is completely immutable.

**WARD:&nbsp;** Ooh.

**JOHN:&nbsp;** That's true. That is true. Absolutely true.

**PASCAL:&nbsp;** [So, if I stand on this…]

**JOHN:&nbsp;** But I think this is great.

**PASCAL:&nbsp;** If I'm standing on this land mine right now I will just stand right here. I do not move but I keep talking. Is that alright?

**JOHN:&nbsp;** [Laughs] Yeah, and I think your post Pascal, you've written a lot of great posts. And I got to tell you, this is one of my favorite posts that I've bookmarked, the 'Change Detection Explained'. Because you do a good job…

**PASCAL:&nbsp;** Thanks so much.

**JOHN:&nbsp;** Not just explaining how technically to do it but you explain why the heck would I even care. And that is so rare in today's technology. And…

**PASCAL:&nbsp;** Thank you. I really appreciate it.

**JOHN:&nbsp;** Good job.

**CHUCK:&nbsp;** Alright. Well, I need to push us into picks because I've got other things going on this evening. Pascal, if people want to see what you're up to or follow up with you, follow you on Twitter, any of those things, what are the best places to go to do that?

**PASCAL:&nbsp;** Yeah, definitely on Twitter. You can either follow me, just @PascalPrecht which is my name or you can follow @thoughtram if you're interested in Angular 2 articles because we regularly publish articles and then tweet them. I think those are the best ways to get in touch with me or to follow me in some way. But other than that, I'm not really interesting. So, you probably want to follow other people.

**CHUCK:&nbsp;** I was so tempted to say that I always thought of it as though tram. But anyway…

**PASCAL:&nbsp;** [Laughs] That's funny. No, it's thought ram. [Laughs]

**CHUCK:&nbsp;** Yeah. No, I knew that. Anyway, let's go ahead and do some picks. Lukas, do you have some picks for us?

**LUKAS:&nbsp;** Oh, do I have a pick. So, I just got a super awesome book that I just ordered off of Amazon. I can't wait for it to get here. It's called 'Professional ADO RDS Programming with ASP'.

**JOE:&nbsp;** Oh my gosh.

**LUKAS:&nbsp;** And…

**JOE:&nbsp;** [Laughs]

**WARD:&nbsp;** [Laughs] Oh goodness. What a weekend.

**LUKAS:&nbsp;** [Inaudible] everybody go and buy this book. The next Angular conference you go to, bring it and have our illustrious John Papa sign the cover. I have just made everyone's month. You're welcome. And that's my pick.

**CHUCK:&nbsp;** [Laughs] Alright. Ward, what are your picks?

**WARD:&nbsp;** Well, I'm going to pick another dead John Papa book then.

[Laughter]

**WARD:&nbsp;** You know, I think he's got one on Data in Silverlight 2. And I think that that was a classic. And I'm picking that.

**CHUCK:&nbsp;** Alright. Joe, what are your picks?

**JOE:&nbsp;** So, I'm going to pick John's picture on the 'Professional ADO RDS Programming with ASP 3.0'.

[Laughter]

**JOE:&nbsp;** This is literally the most amazing sexy picture that I have ever seen. John, you are looking good my friend. You [inaudible].

**JOHN:&nbsp;** Alright. Now I have to say something now.

[Laughter]

**JOHN:&nbsp;** Yeah, so the whole world will know, when that picture was taken we were asked [by] Wrox, it's a Wrox book. They asked us to go to a studio and get pictures taken. So, we did that. And the authors of these different books. And we did that. And while we were there, me being the weird guy that I am I'm like “Hey, let's do a bunch of funny-looking poses.” So, we did. And I sent them the picture I wanted them to use but little did I know the studio sent them all the photos. And they decided not to choose the one that I gave them and instead they gave them one where I was literally sitting on a table giving a strange, weird look [laughs] to the camera. And that's what ended up being an infamy. And now 10 years later I get Lukas making fun of it. [Laughs]

**WARD:&nbsp;** We're back to haunt you.

**JOHN:&nbsp;** [Laughs]

**JOE:&nbsp;** Oh my gosh. It's just beautiful. You absolutely must drop what you're doing, google this book or go to the show notes, and check out that picture. It looks great.

**LUKAS:&nbsp;** And just buy it for a dollar.

**JOE:&nbsp;** Yes.

**LUKAS:&nbsp;** That's what I did. The shipping is more than the book.

**JOE:&nbsp;** That's right.

**LUKAS:&nbsp;** But it's [inaudible]

**JOE:&nbsp;** Paperback for a buck, 15.

**LUKAS:&nbsp;** Yeah.

**JOHN:&nbsp;** So, I asked them to take… we took a backside of that picture too, by the way. I asked them to put it on the back cover but they wouldn't let us do it.

**CHUCK:** [Laughs]

**JOE:&nbsp;** That's too funny. So, I'd also like to pick ZEIT. I'm not even sure if I'm saying that right. Is that how they say it, how Guillermo says it, pronounces it, Chuck?

**PASCAL:&nbsp;** [Inaudible]

**CHUCK:&nbsp;** I don't remember.

**JOE:&nbsp;** Yeah. So, it's Z-E-I-T dot C-O. It's a new service Guillermo Rauch who is one of the more prolific JavaScript bloggers and writes some amazing JavaScript blogs and is a well-respected as being a very smart, good developer has this awesome service.

**LUKAS:&nbsp;** Socket.IO. He wrote that.

**JOE:&nbsp;** What's that? Socket.IO. Yes, there we go. So anyway, this service is totally awesome. Let's say that you're working with an Angular project and you got a Node backend to it. And you want to show somebody a problem or where you're at or something. And who wants to spend 20 minutes to an hour trying to figure out some hosting to throw it up? This is literally an npm tool that you install and all you type in is ‘go’ and then hit enter. And it takes your project in the current directory and throws it up on a website, installs the npm modules immediately, and then gives you this public website you can use. And then if you want to take it to production you can choose your own URL. But it assigns you out a unique URL that other people can go and check out your code. Super awesome. Amazingly fast. They can get it deployed faster than you could npm install the project yourself. Out on the internet. Super cool little product and service. So, I'm going to pick that.

I also am going to pick a game that I've been playing. Overwatch. I picked this n the other podcast, on the JavaScript Jabber podcast. I got to pick it again because it's so amazingly fun. Super fun. I'm pretty sure that in a couple of months I'll be picking some kind of gaming addiction recovery service. [Chuckles] But for now I'm picking Overwatch. Awesome game.

**CHUCK:&nbsp;** Alright. It looks like Lukas and Pascal need to take off. Pascal, do you have any picks you want to throw in real quick?

**PASCAL:&nbsp;** Yeah, yeah. So actually, I would like to take a book by John Papa too but I think I was not on this planet yet when he wrote these books. So, I have to take something else.

**CHUCK:&nbsp;** [Laughs]

**JOHN:&nbsp;** Oh, oh.

**WARD:&nbsp;** Oh.

**PASCAL:&nbsp;** I'm sorry.

[Chuckles]

**PASCAL:&nbsp;** So, one thing…

**CHUCK:&nbsp;** Aren't the old man jokes directed at somebody else usually?

**JOHN:** Yeah.

**WARD:&nbsp;** He so deserves them. He has hair in that picture, too. That's another reason to buy the book.

[Laughter]

**PASCAL:&nbsp;** So, one pick I have is I started a project a month ago called 5thingsAngular which is basically a mailing list where you get weekly updates on five things Angular. And these five things, usually they focus on the development of Angular, the actual development. So, we have links to pull requests and issues. If you are interested in the development of Angular 2 then this mailing list gives you every week updates on what's going on, because it's super hard to keep track nowadays. And…

**JOHN:&nbsp;** It's very good. It's very good.

**PASCAL:&nbsp;** My second pick is actually something I've experienced together with Joe Eames in [inaudible] after ng-conf. So, I had this drink called Dr Pepper which I didn't know. And it's super yummy. So, Dr Pepper is my second pick.

**WARD:&nbsp;** That is the stand-by of programmers everywhere and DP stands for data processing as well as Dr Pepper. So, you're…

**JOE:&nbsp;** [Laughs] Yeah, that's what you drink…

**CHUCK:&nbsp;** That's so true.

**JOE:&nbsp;** When the machine is out of Mountain Dew.

**WARD:&nbsp;** [Laughs] Bring it back.

**CHUCK:&nbsp;** John, did we get your picks?

**JOHN:&nbsp;** Yeah, so, I have two picks. One of them is a place called NOMAD. It's at HelloNomad.com. They make these nice little things that you can use for your iPhone, iPad, et cetera, or your Android device. One of them that I love is a USB lightning dongle that you can put on your keychain. It's only an inch and a half long. And I use it all the time. It's fantastic for connecting your laptop to your phone to charge it or even in your car when you just need one of those wires. They also make chargers and make the car charger stuff, too.

The other thing, my other pick, is my favorite one here today. It's Gilderoy Lockhart who I just realized, this is an actor, Kenneth Branagh I believe is his name. He's in Harry Potter the second movie. And he is Ward Bell's lookalike. If you look at the link that we put in here, this guy, I think Ward Bell is moonlighting as an actor.

**WARD:&nbsp;** Okay.

**CHUCK:&nbsp;** Yeah, especially if you go look at his old tech books that he wrote on .NET and stuff.

**JOE:&nbsp;** [Laughs]

**WARD:&nbsp;** [Laughs] Yeah, right. I actually, I have that cape.

**JOHN:&nbsp;** You do. I know. And that's your hair.

**WARD:&nbsp;** Oh, no. Well, at least…

**JOHN:&nbsp;** [Laughs]

**WARD:&nbsp;** Alright. [Inaudible]

**CHUCK:&nbsp;** I'm also going to throw in there that if you click on John Papa's name on the book that Lukas recommended I don't think he has an author page in there. So, it just takes you to a search for John Papa. And the first two listings are 'The Tarot' and 'The Tarot Book 2'. So…

**WARD:&nbsp;** Well, John's work on 'The Tarot' is absolutely fundamental.

**JOHN:&nbsp;** [Laughs]

**WARD:&nbsp;** So, if you're looking into your future you've got to get his book on tarot card reading. It'll have John tell your future.

**CHUCK:&nbsp;** Yeah.

**JOHN:&nbsp;** And we are completely off the reservation. [Chuckles]

**CHUCK:&nbsp;** Alright. I've got a couple of picks I'm going to throw out there really quickly. The first one is that you can do PowerPoint or Keynote presentations, Keynote, not PowerPoint. I guess you might be able to do PowerPoint. I haven't tried. Anyway, on the iPad. And when I was at ng-conf they were giving out these cube projectors which are really small. They're a couple of inches square. Cube, whatever. And they have a battery in them so you don't even have to plug them in. And you can fit them in your bag when you go places and have to present. I actually wound up doing a presentation to about 50 to 75 Cub Scout leaders last week and was using slides. And I just popped that thing out of my bag, pointed it at the screen. It worked great. If you're going to do it on your iPad you need a lightning cable to HDMI adapter. But they sell those and they're not terribly expensive. So yeah, I'm going to pick the adapter and the cube projector.

And then finally I also have another pick that's a book pick. And this is something that I read a week ago and it really, really impacted me. It's a book called 'Fully Alive' by Ken Davis. Ken is a businessman from Nashville I think. And anyway, the book just goes into how to be successful in live, not just successful in business and talked a lot about how to live fully alive. And how most people go through life just coasting and not really living. And he talks about all kinds of different areas of life and the kinds of things that you need to be doing in your life in order to live fully alive. And I think the advice is pretty good for just about anybody. Some of it's fairly specific but most of it is just getting you to that place where you light up and you live. So anyway, I'm going to pick that book.

And half of our panel is gone so I'm just going to go ahead and wrap the show. Thanks everyone for coming and we'll catch you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wanna have conversations with the Adventures in Angular crew and their guests? Do you want to support the show? Now you can. Go to AdventuresInAngular.com/forum and sign up today!]_**
