# Term 4 Competency Assessments


## Final Competency Assessment

### Design
#### Developing
The task to integrate 3D Secure that I was working on ended up being sidelined due to time constraints. I packaged up the work and planning I did on this project so that it can be revisited in the future. Hopefully I will get to revisit this project as I enjoyed it overall. 

I learned a lot about managing others expectations during this term. This 3D Secure project relied on many pieces of our application working together and this led to time delays. For example: we couldn't update our version of Java easily so that limited the Stripe library we could use. This let me down a development path that turned out to not be what we wanted. 

### Engineering Tools
#### Developing
One major drawback I encountered while trying to use Stripe PaymentIntents is that they can only be used during the actual payment process when a credit card is being charged. This is not exactly what we were looking for. We wanted to introduce 3D Secure but ideally we wanted this verification step to occur when a user is saving their credit card details for future use. The can be accomplished with what Stripe calls SetupIntents, but we did not have easy access to SetupIntents with the Stripe library version we were limited to.

In a future iteration of this project we will either have updated our Java version so that we can use the latest Stripe library version and have access to SetupIntents, or we will build our own custom interface library to interact with Stripe's general API. The latter choice would involve more custom work.

Again, I have gained a lot of knowledge about Stripe's API. This knowledge will be valuable in any setting where credit cards and payments are handled.

### Computer Information Processing and Algorithms
#### Developing
In addition to the library limitations I ran into, there was also the complication of our legacy funding flows adding complexity to the project. The main issue arose while attempting to add a new state to a payment. This new "requires user validation" state for 3D Secure validation did not work well for a few reasons.

For example, we were hoping to provide information about successful 3D Secure validation on our admin dashboard for use by admins when they are authorizing certain payments. The issue being that using Stripe PaymentIntents, 3D Secure validation can only happen as the payment is processing. Therefor we cant provide this information on the admin dashboard prior to payment processing. 

Using Stripe SetupIntents would allow us to get 3D Secure validation earlier on in the process such that we could use this information to inform our admins authorizing payments manually and even allow for further automation of our system.


## Mid Term Competency Assessment

### Design
#### Developing
In working through this project to integrate 3D Secure into our funding flow many complexities have arisen. Our Stripe library was out of date and could not be updated to the latest version available because of our Java version. This forced us to change the project slightly. An important piece of 3D Secure is unavailable with the library version compatible with our system. This forced us to move when we are performing 3D Secure from when we collect the credit card details to where the user is making a purchase.

This was a good experience in testing the bounds of the project and seeing what we can fit in in the time frame. 

### Engineering Tools
#### Developing
I have learned much about Stripe's API. Specifically I am gaining understanding on how their Intents system works. Rather than just creating a Charge when you intend on charging your user you create what is called a PaymentIntent as early as you can. You can then update it as you need with different payment methods that the user chooses and different amounts to charge. Then you can attempt payment on their card which can trigger the additional 3D Secure validation.

One benefit of all this is you can track in more detail the life cycle of this purchase and payment and if it is abandoned you can see exactly at which step it was abandoned.

### Computer Information Processing and Algorithms
#### Developing
Stripe makes handling credit card numbers easy and secure. They provide front end tools to collect and handle the card number itself securely and they provide us with a token representation. We can then use that token in place of the card number within our system. This means we actually never collect and handle the credit card details ourselves and our processing provider Stripe handles everything.

Beyond handling the credit card number, our funding logic needs quite a bit of rework. It was never set up in a way that a funding event can be in a "needs validation" state like it is when 3D Secure validation is required from the user. This is taking the bulk of my time. We have multiple avenues where a funding event can be triggered (our webapp and our API for example) and they share this funding logic. This may need to be split into multiple paths.

Planning this refactoring has been the biggest challenge and area of growth for me. 


## Learning Objectives

### Design
#### Description
Gathers requirements, develops models and creates prototypes in a timely and effective manner to increase a project’s safety and success
Examples:
* Gathers full requirements for a project
* Understands the client’s needs
* Models a solution using the appropriate tools
* Relates and justifies the design process to the client
* Implements designs that are safe and effective
* Demonstrates awareness of how the design integrates into its environment
	
#### Developing
All learning objectives are related to the same credit card validation project.

My main goal overall this term is to lead a larger and more complex project than I have before. I have been assigned the project of integrating 3D Secure into our credit card system. 3D Secure is a verification technology supported by major credit card providers.

I will be the lead developer on this project with some support from our lead designer. This project has a strict deadline. After some initial investigation into our current code for handling credit cards and also the documentation for this API, I intend on formulating a plan for building this feature that I will then validate with our development team.

The hope is to build on my skills in project management and time management.


### Engineering Tools
#### Description
Uses a broad range of Engineering tools, applications and software.
Examples:
* Designs equipment and systems using a variety of software packages
* Simulates mechanical and electronic systems using the appropriate tools
* Analyses systems, equipment and data using the correct tools
* Operates mechanical equipment in a lab or workshop safely and effectively
* Uses electronics and electrical equipment in a careful and accurate manner
* Develops software and scripts in a variety of environments and languages
* Uses computer software and systems in an appropriate manner
* Understands database concepts and usage and uses them effectively
* Researches and recommends new tools where existing tools are inadequate
* Chooses tools based on their comparative strengths and weaknesses
	
#### Developing
All learning objectives are related to the same credit card validation project.

For the credit card project I am doing this term, I will be working heavily with Stripe's APIs. Stripe is a platform we use to process credit cards. They provide an API for 3D Secure which we want to integrate into our application.

Stripe is a very popular provider of financial APIs so I am excited to get experience working with their APIs and plugins, both on the front-end and back-end.


### Computer Information Processing and Algorithms
#### Description
Understands the theoretical foundations of computer science and the practice of abstracting known methods to new problems
Examples:
* Designs automated software test tools
* Displays an ability to manipulate information
* Creates solutions from user specifications, given known system constraints
* Optimizes solutions to improve performance using coding best practices
* Acknowledges the practical limits of a system for problem solving
	
#### Developing
All learning objectives are related to the same credit card validation project.

Never in my development experience have I worked with credit cards before. Credit card numbers and related details are sensitive information. I want to learn best practices around handling credit card details.

Integrating this new 3D Secure service is also a breaking change to our credit card funding process. I will need to engineer a solution to ensure our existing customers with saved credit card information are unnaffected by this change. Only new credit cards should be verified with 3D Secure.
