# Semester 3 Portfolio Mike van Engelen

## Table of contents:
- [1. Intdroduction](#Introducation)
- [2. to do list](#To-do)
- [3. Learning Outcomes](#Learning-Outcomes)
  - [3.1 Web Application](#1-Web-application)
  - [3.2 Software Quality](#2-Software-quality)
  - [3.3 Agile Method](#3-Agile-method)
  - [3.4 CI/CD](#4-CI/CD)
  - [3.5 Cultural differences and ethics](#5-Cultural-differences-and-ethics)
  - [3.6 Requirements and Design](#6-Requirements-and-Design)
  - [3.7 Bussiness Process](#7-Bussiness-Process)
  - [3.8 Professional](#8-Professional)

## Introducation:

This Git repository contains all my projects, documentation and where to find everything.

This Git repository contains 2 projects:
- Volksmond (individual project):
The current political system has been stagnant and more and more people don't agree with the actions of politicians. Change is needed and with my project I want to make an experimental alternative. Currently we have a representative democracy where citizens can only influence politics by voting for a represantative who makes all the descisions for you. What if you could have direct conversations with people online, come up with solutions and vote for the best one?

- GroopySwoopy (group project): It's sometimes hard to choose a movie to watch, especially with friends. This project solves this by having an app where you can create a group with your friends and swipe movies like in Tinder. When all people match with the same movie, you have a movie to watch!

## Documentation
This folder contains all the documentation for my reasearches, designs and choices.

## Learning Outcomes
This folder contains both the Learning outcomes for the Group Project and the learning outcomes for the Individual Learning outcomes.

## Project
This folder contains all the project information. It consists of all the code and other information. 

## Learning Outcomes:

| # | Name | Short description | Clarification |
|---|------|-------------------|---------------|
| 1 | Web application | You design and build **user-friendly, full-stack** web applications. | **User friendly:** You apply basic User experience testing and development techniques.<br>**Full-stack:** You design and build a full stack application using commonly accepted front end (Javascript-based framework) and back end techniques (e.g. Object Relational Mapping) choosing and implementing relevant communication protocols and addressing asynchronous communication issues. |
| 2 | Software quality | You use software **tooling and methodology** that continuously monitors and improve the software quality during software development. | **Tooling and methodology:** Carry out, monitor and report on unit integration, regression and system tests, with attention for security and performance aspects, as well as applying static code analysis and code reviews. |
| 3 | Agile method | You **choose** and implement the most suitable agile software development method for your software project. | **Agile method:** You are aware of the most popular agile methods and their underlying agile principles. You are able to implement the process of your software project according to a chosen methodology. |
| 4 | CI/CD | You **implement** a (semi)automated software release process that matches the needs of the project context. | **Implement:** You implement a continuous integration and deployment solution (using e.g. Gitlab CI and Docker). |
| 5 | Cultural differences and ethics | You **recognize** and **take into account** cultural differences between project stakeholders and ethical aspects in software development. | **Recognize**:  Recognition is based on theoretically substantiated awareness of cultural differences and ethical aspects in software engineering.<br>**Take into account:** Adapt your communication, working, and behavior styles to work with other developers from different cultures;<br>Address one of the standard Programming Ethical Guidelines (e.g., ACM Code of Ethics and Professional Conduct) in your work. |
| 6 | Requirements and Design | You analyze (non-functional) requirements, elaborate (architectural) designs and validate them using **multiple types of test techniques**. | **Multiple types of test techniques:** You apply user acceptance testing and stakeholder feedback to validate the quality of the requirements. You evaluate the quality of the design (e.g., by testing or prototyping) taking into account the formulated quality properties like security and performance. |
| 7 | Business processes | You analyze and describe **simple** business processes that are **related** to your project. | **Simple:** predominantly sequential processes with one or two alternative paths.<br>**Related:** understanding the relationships between the process and software. |
| 8 | Professional | You act in a **professional manner** during software development and learning. | **Professional manner:** You develop software as a team effort according to a prescribed software methodology and following team agreements. You are able to track your work progress and communicate your progress with the team.<br>understanding the relationships between the process and software. |

## 1 Web application

You design and build user-friendly, full-stack web applications.

Clarification:

User friendly: You apply basic User experience testing and development techniques.

Full-stack: You design and build a full stack application using commonly accepted front end (Javascript-based framework) and back end techniques (e.g. Object Relational Mapping) choosing and implementing relevant communication protocols and addressing asynchronous communication issues.


### how I plan to show this learning outcome in my project: 

For this project I'll be making a full stack application with a React frontend for some extra software quality. I choose React because it is generally the most used javascript-framework for frontend development, so I found it useful to learn. Also I have some previous experience with VueJS and wanted to expand my knownledge by trying something slightly different.
I opted to write React in TypeScript for extra software quality thanks to it's typed nature. This prevents unexpected errors and catches them before even building the project. I have virtually no experience with TypeScript.

The web API will be build with ASP.NET Web API core, which we also use in the group-project and is thus easier to learn over the course of the semester. The API is connected with an Azure hosted SQL database through Entity Framework core (code-first) because it integrates nicely with ASP.NET.
When using Entity Framework I've learned it can be fiddly with changes made to the models. New migrations might not be able to update the database properly and require a full database and migration sweep.

To get a sense of what I have to built I made a few designs. The style is inspired by Reddit, since it's the inspiration structure of the project.

**Homepage with all posted problems**
![Web 1920 – 1](designs/design-homepage.png)

**Problem page with all posted solutions**
![Web 1920 – 2](designs/design-discussionpage.png)

**Solution page with all comments**
![Web 1920 – 3](designs/design-solutionpage.png)


## 2 Software quality

You use software tooling and methodology that continuously monitors and improve the software quality during software development. 

Clarification:

Tooling and methodology: Carry out, monitor and report on unit integration, regression and system tests, with attention for security and performance aspects, as well as applying static code analysis and code reviews.

### how I plan to show this learning outcome in my project: 

There are multiple ways to test an application. For my project I intent to use User Experience testing (UX), Unit testing (backend) and Integration testing (frontend).

### UX tests
**Objective:** Making sure users understand the intended use and effortlessly navigate the application.

Xamara (My girlfriend): She found the design very simplistic and lacking context, but when I told her the concept and explained it a bit she began to understand the UI more. She said the structure makes sense and also figured I used Reddit as an inspiration, especially for the comments. She suggested showing more information in all cards to provide more context for the user.


### Frontend tests
**Objective:** Making sure the frontend renders as expected and that forms work.

For this I have use Jest. The tricky part was forcing Jest to first transform the TypeScript files into readable JavaScript. Also the imports didn't work at first, but had to set isolatedModules in the tsconfig.json to false.

- Verify that the Home Page renders the create citizen form.
- Verify that the Home Page renders the create solution form.
- Verify that the Solution Page renders the suggested solution section.
- Verify that the Referendum Component shows a message when the discussion has no solutions.
![frontendTest](Screenshots/frontendTest.jpg)

### Unit tests
**Objective:** Making sure individual controller functions work as intended.
- Verify that a user can upvote a reply.
- Verify that a user can remove a vote on a reply.
- Verify that a user can reply on another reply recursively.


### Integration tests
**Objective:** Making sure that the backend works and connects and interacts with the database.
I used Postman for this. When an object is Posted, the api sends the ID back. This ID is used as variable for the other requests.

#### Citizen test scenarios:
- Verify that a citizen can be created.
- Verify that all citizens can be fetched.
- Verify that a citizen can be fetched by Id.
- Verify that a citizen can be deleted.

![integrationTestCitizen](Screenshots/integrationTestCitizen.jpg)


#### Discussion test scenarios:
- Verify that a discussion can be created.
- Verify that all discussions can be fetched.
- Verify that a discussion can be fetched by Id.
- Verify that a discussion can be deleted.

![integrationTestDiscussion](Screenshots/integrationTestDiscussion.jpg)


#### Solution test scenarios:
- Verify that a solution can be created.
- Verify that a solution can be upvoted.
- Verify that a solution can be downvoted.
- Verify that a vote can be revoked.
- Verify that all solutions can be fetched.
- Verify that a solution can be fetched by Id.
- Verify that a solution can be deleted.

![integrationTestSolution](Screenshots/integrationTestSolution.jpg)


### Code scan
I've ran my frontend through SolarCloud's code scan for extra software quality control.
![codescan](Screenshots/codescan.jpg)

## 3 Agile method

You can implement the software process for your project according to a given agile software development method.

Clarification:

Agile method: You are aware of most popular agile methods and their underlying agile principles. You are able to implement the process of your software project according to a chosen methodology.

### how I plan to show this learning outcome in my project: 

As an Associate Degree student I've been given Scrum as Agile method I must apply to my software development process.

Scrum is an iterative process were you get feedback every sprint and apply it in the next sprint. This makes software development more flexible and adaptable to the stake-holders wishes.

Scrum consists of 5 key elements:
1. Product backlog: This is a list of user-stories which are prioritized by the stakeholders wants and needs.
2. Sprint planning: Before the start of every sprint, the developer(s) and the stakeholder(s) prioritize user-stories which ought to be finnished at the end of the sprint.
3. Daily stand-up: At the start of every (work-)day the team gets together for a meeting. The Scrum-master asks everyone what they plan to do that day and ask if they need help.
4. Sprint review: At the end of each sprint, the sprint results are presented to the stakeholders. This is important to get feedback to implement in a future sprint.
5. Sprint Retrospective: The retrospective should happen closely after the sprint review. It's about reflecting on what went well and what went wrong in the development process in the last sprint.

#### Scrum boards evidence
Backend (https://github.com/orgs/Fontys-OAMK-Beter/projects/2)

Frontend (https://github.com/orgs/Fontys-OAMK-Beter/projects/3/views/1)

Learning to work in Agile has been difficult at first, especially keeping the scrumboard up to date. But after feedback and us as a group reminding eachother everytime, we improved overall and saw that implementing Agile in or development process really improves the organization and teamwork.

## 4 CI/CD

You implement a (semi)automated software release process that matches the needs of the project context.

Clarification:

Implement: You implement a continuous integration and delivery solution (using e.g. Gitlab CI and Docker).

### how I plan to show this learning outcome in my project: 

The backend api is made with Docker gets build and deployed to an Azure Container App whenever a commit is pushed to the GitHub main branch. I would protect the main branch from direct pushes, but that requires upgrading the organization the repository is in.
Github Actions says the action failed, since it throws an error when it tries to logout, but that doesn't impact the deployment itself.

![cicdbackend](Screenshots/cicdbackend.png)


The frontend also gets built and deployed whenever a commit is pushed to the Github main branch. The frontend is hosted as an Azure Static Web App.

![cicdfrontend-notest](Screenshots/cicdfrontendNotest.png)

I've also tried adding a frontend test to the pipeline, but I get errors because I can't get Jest to work with TypeScript. I've tried to resolve this by letting babel preprocess the .tsx files before the test runs and tried to swap Jest for ts-jest. But I couldn't get any to work.

![cicdfrontend-test](Screenshots/cicdfrontendTest.png)

After more fiddling with the frontend testing, I have got the test to work and included it into the Github Action.

![cicdfrontend-test-success](Screenshots/cicdfrontendTestSuccess.png)

#### After deployment:
https://happy-flower-043bad603.3.azurestaticapps.net/


## 5 Cultural differences and ethics

You recognize and take into account cultural differences when working with multi-site teams, and are aware of ethical aspects in software development.

Clarifications:

Recognize: Recognition is based on theoretically substantiated awareness of cultural differences and ethical aspects in software engineering.

Take into account: Adapt your communication, working, and behavior styles to work with other developers from different cultures; 

Address one of the standard Programming Ethical Guidelines (e.g., ACM Code of Ethics and Professional Conduct) in your work.  

### how I plan to show this learning outcome in my project: 



### What is culture?

Culture is the ideas, beliefs, values, norms, practices and symbols a society upholds. These factors are reflections of their economic and social structures.
Usually a society has one dominant culture, but can have many sub-cultures. Especially in today's day and age has culture become more fluid. Globalization, thanks to high-speed transport and the internet, has led many cultural aspects to mix. Yet cultures are still **very disctinct**, since cultural changes are slow to manifest. This is because cultures are defined by their material and historical conditions, which are hard to change.

### what is my culture?

I find defining my own culture to be very hard, since I disagree with a lot within my own society. This has led me to not identify with the place where I was born nor live. I think it's way more important to critically reflect on the culture you've been brought up with and adapt better ideas, beliefs and values.

That being said, I've been brought up Limburgisch and some say we're comparatively quite hospitable. That means we welcome new people with open arms and treat our guests as good as possible.

Another trait which applies to me is Dutch directness. Obviously there are boundaries, but I'm more inclined to say something weird, unexpected or even a little bit taboo.

One cultural trait we (and I) have as Dutch people is that we need to plan everything. Spontanious visits are foreign to us, even by friends or family. Personally I'd like to see this changed in my life, but late stage capitalism makes this increasingly hard.

Also, according to the Lewis Cultural Model, Dutch people tend to be quite far removed from the Reactive variation. I personally find myself to be quite reactive. I like to listen to and understand context first. I think everything in life is multi-fasceted, which requires broader understanding first. This also creates better harmony and empathy for eachother, which I find very important because it's the basis for good human connection.


### What did you do to improve the group communications with respect to cultural differences?

In our group project, we've had a few different cultures mixed. We've had to work with students from Finland, who tend to be quite shy at first. Our Dutch directness definitely helped in breaking the ice, even though it was weird for the Finns. This doesn't mean that the Finnish students all suddenly became as direct as us. This made it hard to sometimes know what they actually thought of some descisions and situations.

When we were working on the project I've noticed we as Dutch people can be quite loud sometimes. This could be distracting, ironically mostly to ourselves. To counter this we tried to remind eachother when we were talking too much.

![theLewisModel](graphs/theLewisModel.png)
This is the Lewis Model, which categorizes the worlds cultures in 3 parts: Multi-active, reactive and linear-active.
The Netherlands and Finland both are closest to Linear-active. This means we are organized planners, task-oriented and bureaucratic. However, Dutch people are a tiny bit leaning to Multi-active and Finns are somewhat more alligned to the Reactive side, which means they prefer to listen before forming an opinion and speaking. This was very noticable with us as Dutch people were shouting our ideas for the project left and right, where as the Finnish people seemed to prefer to listen first and then respond or add to our ideas.

### Ethics in software engineering

To show I understand the ethics within software engineering, I'll use the Technology Impact Cycle Tool (TICT) with regards to my individual project.

#### Intended solution
The application should allow all citizens to equally voice their opinions on social issues, suggested solutions and even suggest their own solution. After some time, discussions close and a referendum starts where citizens can vote for their preffered solution.
This should better represent the wants and needs of society, instead of well-off politicians, who can be detachted from the general public, choosing for them.

#### Possible stakeholders
Everyone living in the country where this would be implemented would be affected by this, since it's political. This is quite risky, but so is the current political system.

#### Privacy
Privacy is a huge concern with this application and there are many unanswered questions, like should all citizens remain anonymous on the site for safity, or should names be displayed for accountability. Where, how and how long should all the data be stored? Who has acces to this data? These and more questions should be majorly researched, people should be interviewd and these questions are not mine to answer since it's about the general publics most important aspects of life.

#### Sustainability
Sustainability-wise it shouldn't be more impactful for the environment than any other application. The servers probaly are the most environmentally taxing in this case.

#### Fairness
There are also many fairness concerns, like with any political system. In this case it's about minority groups who have contrasting values with the general public and digitally illiterate people.
In a democracy that uses a majority vote, minorities can often get left out and not listened to. This is why we need to get as close to consensus-democracy as possible without making it impossible to pass new laws. However, this is in the current political system also a problem.
For digitally illiterate people, there could be help-desks at city halls or call-centres. Even with this help this wouldn't be a perfect solution, since it would still be harder for them to participate than average because getting help takes longer.

#### Data
See privacy.

#### Human values
This project plays into the values of equal rights, democracy and political freedom. It gives the power directly into peoples hands. This does however mean that we become more dependant on eachother, instead of elected politicians, which makes the collective bigger. Since the Netherlands is considered more individualistic, this could pose a problem in acceptance of this project.

#### Bad actors
As said in the fairness section, majority vote can cause problems for minority groups and in bad cases could lead to actual harm. That's why I would want to include more features into this application that requires citing scientific sources when suggesting solutions for a social issue.
Also hacking would be a huge problem. If there is a vurnability in the application, people can and will exploit it, which for a political system is very bad. There's not much you can do about this except hire a big security team.

#### Transparency
The question for such projects is if the code should be public or private. If it's public, it can be more trusted, but bugs are easier to find and exploit. If it's private, people must simply trust the developers, but bugs are harder to find and exploit. I don't have a definitive question for this.

#### Future impact
Utopia: Society maturely discusses social issues on the platform and comes up with well-researched solutions and votes for what is best for society as a whole. If this happens, problems can get fixed faster, society is more reactive and true democracy has been established.

Dystopia: Society gets fragmented because people can't agree. In the worst case, there might be a civil war cause by dissagreements and ideological groups are forming. No issues get resolved, only argues about.

As we can imagine, the stakes for such a project are immensly high. But so is any possible political system. But frankly, these possible futures exist with or without this app. That is not to say that my platform is the definitive solution.

## 6 Requirements and Design

You translate (non-functional) requirements to extend existing (architectural) designs and can validate them using multiple types of test techniques.

Clarifications:

Multiple types of test techniques: You apply user acceptance testing and stakeholder feedback to validate the quality of the requirements. You evaluate the quality of the design (e.g., by testing or prototyping) taking into account the formulated quality properties like security and performance.

### how I plan to show this learning outcome in my project: 

### Conceptual model (ip)
![conceptual-model](designs/conceptual-model.jpg)
This model consists of 2 parts. The right side of 'Citizen' is about the social media part of Volksmond. This means it's about the normal every day social media usage such as posting on your feed and commenting on other people's posts.

The left side is about discussions that arose from the social media platform. Here people can further discuss a certain topic and come up with solutions and vote during a referendum.

### Database design (ip)

Even though I use Entity Framework (code-first) in this project, I still decided to create a database design. This helped me reverse-engineer how the code should look like to help me visualize.

![conceptual-model](designs/database-ontwerp.jpg)

### Database design (gp)
![groopySwoopyDB](designs/gsDb.png)

### C4 model (ip)

![c4-model](designs/c4.jpg)

### Individual project designs:
[See Web Application at top of portfolio](#1-WebApplication)

### Group project designs:
![groopySwoopyGroups](designs/gsGroups.png)
![groopySwoopyEvents](designs/gsEvents.png)
![groopySwoopyProfile](designs/gsProfile.png)

### UX Tests (ip)
#### When I simply showed the designs:
- Xamara (My girlfriend): She found the design very simplistic and lacking context, but when I told her the concept and explained it a bit she began to understand the UI more. She said the structure makes sense and also figured I used Reddit as an inspiration, especially for the comments. She suggested showing more information in all cards to provide more context for the user.

#### Usability tests:
When my frontend is done I'll take 3 groups to test the User-Experience. 2 Software peers who have good knownledge of programming, 2 non-software peers who have little to no programming skills and 2 digitally illiterate people who have (some) trouble navigating the internet. I sit them in front of the computer with the website open on the homepage and give them 5 tasks:
1. Search for a discussion about global warming.
2. Leave a like on the most liked comment in a solution.
3. Reply to the latest comment in a solution.
4. Find a discussion that has an active referendum and vote for a solution.
5. Start a new discussion.

These tasks are multi-stepped which leave room for interpretation. This makes for a more realistic test scenario and what users most likely will actually do in the application.

#### Testers:
- Software peers: Brian, Ruben, Wouter.
- Non-software: Xamara, my brother.
- Digitally illiterate: my Mother, my uncle.

## 7 Bussiness Process

You can explain simple business processes and relate them to the development of your software project.

Clarifications:

Simple: predominantly sequential processes with one or two alternative paths

Relate: understanding the relationships between the process and software.

### how I plan to show this learning outcome in my project: 

## stakeholders analysis:

### what is a stake holder?

A stakeholder is a person or organization that has rights, shares, claims, or interests concerning the system or its properties meeting their needs and expectations.
These people thus have reasons to make and/or influence descisions made in a project. These descisions could be about requirements, deadlines and costs.

### Who are the stakeholders in my project and what are their goals and constraints? 

In the group project we have 3 stakeholders: Frank Schurgers, Meija Lohiniva and Samuil Angelov.
Their shared goal is to ensure the projects follows the Agile Scrum method and that the international collaboration goes as smooth as possible.

## Process analysis:

### What is a business process? 

A business process is a series of activities and descisions done by an organization to generate an output with value.

I have visualized two business processes relating to my individual project.
The first one is the current process needed to make national descisions. It describes the current voting process.
1. A registered and elligable citizen receives a voting bill in their mail.
2. The citizen (preferably) researches all the options.
3. The citizen goes a local voting booth.
4. The citizen chooses who they deligate their vote to.
5. The citizen must hope that the citizen they choose follows through on promises.

![businessprocess-old](designs/businessprocess-old.jpg)


The second diagram is the new process I envision with Volksmond.
1. A registered and elligable citizen discusses social issues on Volksmond.
2. After some time a referendum starts.
3. The citizen can votses for their preffered solution.
4. If enough people vote for the same solution, it will get sent to the appropriate ministries.

![businessprocess-new](designs/businessprocess-new.jpg)

## 8 Professional

You act in a professional manner during software development and learning.

Clarification:

Professional manner: 

You develop software as a team effort according to a prescribed software methodology and following team agreements. You are able to track your work progress and communicate your progress with the team.

You  independently recognize and decide where your knowledge falls short to solve a software problem and  communicate which new knowledge and skills you need to learn.

### how I plan to show this learning outcome in my project: 

To demonstrate my understanding of this learning objective, for our group project, we organized presentations where stakeholders gave us feedback on our work. Afterwards, we had group discussions to carefully examine and address the feedback we received.

My individual project has been a struggle, thanks to sickness and the conceptual difficulty of my project. My project idea was not realistic to conceptualize, design and develop since the project is about a very difficult problem which simply cannot be solved that easily. I was stuck for a long time in the phase of research and brainstorming how I should tackle the problem. This led me to lose track of the actual learning outcomes and focus on politics instead without result. When I eventually learned to drop this and focus on what I'm actually supposed to do and learn in this semester, everything when much better and faster. That's when I got a lot of feedback from my teachers and implemented them as fast possible for my next feedback. This has definitly been a lesson for me to focus on the actual task at hand, instead of trying to solve the world with one 'simple' solution.
