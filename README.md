# The Royalty Off Revenue License

## Intro

The motivation for this license is that "freedom free" is good, but "beer free" is not, because economic incentives get things done.

Whenever a robotics company tries to make a robot, they can write all the code from scratch, or lean on the work of volunteers in the form of open source software.  This is not working well.  The systems are too complex for one company to do everything, and volunteers tend to primarily focus on the core moving parts of software, often paying less attention to less interesting, but high value, parts, such as documentation, unit tests, ease of use, and interaction with other programs.  There are exceptions to this, but they are the best of the best, where instead it could be run of the mill.

The core problem is that existing software licenses provide no direct incentives to improve existing software or create software to fill a need.  If I have a cool idea for a software library that could save a lot of people a lot of time just by coding it up and posting it on Github, I can't just slap an existing license on it and "let the cash roll in".  If I find room for improvement in an existing open source library, there is a tragedy of the commons scenario where everyone gets just the same benefit no matter who puts in the work.

Generally, there is currently no easy way to take advantage of the specialization and massive economies of scale that software is naturally suited for (software should have ALL of the economies of scale).

---

## Perspectives we care about

### Library developers

Library developers are making tools to fill needs.  They tend to work on their projects in their spare time, rather than for money as a job.

### Businesses

Businesses want their tools to be easy to use as well as well tested, documented, and supported.  Also cheap, but sometimes you have to spend money to make money.

### Personal use / Pre-revenue startups

These people tend to have small budgets, and want their software usable and free.

---

## Desirable license features

### Open source

By which, we mean anyone can see the source code, not necessarily free to use ("Free Software" here refers to that).

If someone can read, compile, and run the code, all on their local machine, they can trust that they know what they're running.  It's well established that open source code is generally more secure than closed source code.

### Anyone can contribute

With open source code, anyone can code up improvements to a library or application.  One of the great strengths of Free Software projects is that those people can easily contribute back to the project with a fork or pull request.

### Modifications to the code must be disclosed

There is a lot of duplicated work done by multiple companies trying to accomplish the same thing.  They all hide their code, and work is wasted.  By forcing disclosure of code modifications, that duplicate work is eliminated.

On the other hand, when that disclosed code can be used for free by competitors, a free-rider problem arises, where everyone but the first person to put in the work gets all the benefit for free.  There needs to be a way to put a price tag on the disclosed code, so both duplicate work and a free-rider problem can be avoided.

### Costs money

"But wait", you say, "isn't free good?"

There is no such thing as a free lunch.  If a developer isn't getting paid for their work, they have no incentive to make their software useful for money-making applications, no incentive to spend time on the boring parts like documentation and unit tests, and no incentive to keep supporting the project for a long period of time.

The greatest weakness of Free Software licenses is that, while it is possible for anyone to improve a project themselves, they would need to do so for free.  Those that live by the phrase "if you're good at something, never do it for free" generally don't donate their time to the project.  Work has value.

The least "fun" parts of making a library, such as testing, documentation, and long-term support, are often the most neglected, while also being some of the most valuable.

#### Cost is proportional to money gained from its use (royalties)

This provides a direct incentive for library developers to make libraries better for businessess.  Beyond just attracting new users and being better than the next option, this directly incentivizes improvements for existing users too.  The more money the users make, the more money the developer makes.  It's win-win.

This has the side benefit of being free for people who don't make money off the use of the library, such as students, hobbyists, and pre-revenue startups.  All have shoe-string budgets, and potential for revenue in the future.

#### Cost is proportional to revenue (rather than profit)

Profit can be easily manipulated by tricky accounting.  Revenue is much less ambiguous.

### Easy to include in another project

Another strength of the Free Software licenses is that having all the conditions of use clearly shown in the license allows potential library users to make a decision ahead of time, and simply include the code if they want to use it.  This allows for massive trees of libraries including libraries including libraries, the abstraction making life easier for everyone.  Needing to negotiate the cost of the license for each use would be time prohibitive for all parties.

A key aspect of being easy to include in a project is keeping the conditions of the license local to the covered code.  For instance, like how the LGPL only requires changes to the library to be published, rather than the code of the entire project that includes the library, like the GPL.

---

## Current licensing options

There are really two main questions to consider for each of these options:
  1. Would someone use a library under this license?
  2. Would someone apply this license to code they are writing?

### GPL/LGPL/AGPL

Free to use, and you need to recontribute changes made to the code.  This is bad for business owners to apply to their code, because then anyone can use the code without giving them money for it.  LGPL licensed libraries are good to use, because they're free and the license is limited to the library, but the GPL and AGPL are more virulent, and would affect the rest of the codebase.

### Dual licensing

GPL unless you pay for a proprietary license, this option offers a path to monetization for library developers and is free if you don't mind the GPL license, but typically allows proprietary license holders to hide their code and requires negotiation for each license.

There is a lot of freedom in defining the proprietary license, which can be good for businesses, but is more overhead for lone developers.

### Creative Commons (non-commercial)

Totally excludes commercial use.  Unthinkable for businesses.

### Permissive licenses (MIT, Apache 2.0, etc.)

Free to use, and you can hide any modifications to the code.  This is the kind of license businesses like to see in the libraries they use, but the lack of benefits for the library developer or forced recontribution means the quality is often left wanting.


### Software as a service

This is one of the more business-friendly ways of selling software.  It works, but it's not a good solution if you care about latency, security, or have an inconsistent internet connection.

---

## Proposed solution: The Royalty Off Revenue license

Exactly like its name implies, the Royalty Off Revenue license allows anyone to use the licensed software as long as they give the developer a percentage of the revenue earned from its use.

It also defines how contributors to a project under the license can add their own royalties, offering an incentive to contribute (explained in the math section below).

Code under the license that is modified must be disclosed.

The percentage of revenue to be paid is defined by the developer within the license, making it easy for potential users to make decisions.

Overall, the license is intended to be largely similar to the LGPL, with the exception of the royalties.

### The specific behavior we want out of the license:

- If someone modifies your code, they need to make that modified code available (similar to the LGPL)
- If someone makes money by using your code, they need to give you a fraction of their revenue, with that fraction of revenue being defined by the developer within the license
  - Running your code to gain revenue -> pay royalty on that revenue
  - End user buys application that uses your code, and uses that application to make money -> that end user pays royalties
      - (This also incentivizes tools such as editors and compilers)
  - End user buys a robot that is running the library somewhere inside, and makes money by using the robot -> royalty on revenue fom use of the robot, not from the sale
      - (The hardware could easily be configured to not contain ROR-licensed code at the time of sale, and then download it on first startup, so royalties off sale is not feasible)
- If someone modifies your code, they may add their own royalties on top of the existing ones
  - They may NOT remove existing royalties
  - Adding royalties is the ONLY change they may make to the license (TODO: split into an adjacent royalty-tracker file)
  - (As an incentive for them to make your code better)
- The code needs to not cost any money for people who don't use the software to make money
  - "Beer free"
  - No revenue ==> no royalty payment
- If all creators of a piece of software don't add required royalties to the license, this license should be more or less equivalent to the LGPL
- If all users of a piece of software don't get any revenue, this license should be more or less equivalent to the LGPL
- Each contributor to a project should be able to lower their own previously added royalty if they want to.
- Each contributor to a project should be able to raise their own previously added royalty if they want to, though users will still be able to use the lower price from the previous version

TL;DR: Like the LGPL, but you have to pay a percentage of your revenue to use licensed software.

---

### Example use cases:

#### Simple cases

(1) User A *uses* ROR-licensed software and gains revenue from that use
  - ==> Royalty payment on that revenue
  - eg. software as a service:  non-zero revenue ==> non-zero royalty
  - eg. a video game:  zero revenue ==> zero royalty

(2) User A makes Thing B by *using* ROR-licensed software, and sells it
  - ==> Royalty payment on revenue from sale
  - eg. 3D-printing something by using ROR-licensed software
  - eg. writing code with an ROR-licensed editor and selling the results

(3) User A makes Thing B that *contains* ROR-licensed software and sells it
  - ==> No royalty payment
  - eg. A software or device that includes an ROR-licensed library
  - Note that User A could have easily made Thing B not contain ROR-licensed software at time of sale, but download it on first startup

(4) User A makes Thing B, *applies* the ROR-license to it, and sells it
  - Note that in this scenario, User A has made Thing B from scratch, and the only royalties are payable to User A
  - ==> No royalty payment


#### Combinations of simple cases


User A makes Thing B that *contains* ROR-licensed software and *gives* it (no revenue) to User C, who then uses it *without* gaining revenue
  - Simple case (3) applies to User A. ==>  No royalty payment from User A
  - Simple case (1) applies to User C. ==>  No royalty payment from User C

User A makes Thing B that *contains* ROR-licensed software and *gives* it (no revenue) to User C, who then *does* gain revenue by using it
  - Simple case (3) applies to User A. ==>  No royalty payment from User A
  - Simple case (1) applies to User C. ==>  User C pays royalties off of revenue gained by using Thing B

User A makes Thing B that *contains* licensed software and *sells* it to User C, who then uses it *without* gaining revenue
  - Simple case (3) applies to User A. ==>  No royalty payment from User A
  - Simple case (1) applies to User C. ==>  User C pays royalty for revenue gained by using Thing B

User A makes Thing B *using* ROR-licensed software. Thing B also *contains* ROR-licensed software, and User A *applies* additional royalties to it (through the ROR license's mechanism for doing so).  User A then *sells* Thing B to User C, and User C *gains revenue* by *using* Thing B.
  - Simple cases (2), (3), and (4) apply to the initial sale of Thing B. ==> User A pays royalties off the sale revenue for the *use* of ROR-licensed software in the creation of Thing B.
  - Simple case (1) applies to User C. ==> User C pays royalties for revenue gained by using Thing B. Specifically to User A for the applied royalties, and to whoever gains royalties for the ROR-licensed software contained in Thing B

----

The basic idea here is that I took the LGPL V2.1 and more or less slapped a term on it that essentially says "If you use this software to make money, you owe the creator x% off the revenue".

Percentage of revenue means:

 - It's effectively free for students, researchers, and pre-revenue startups.
 - There is a direct financial incentive for the software creator to want the software user to make more money.  The alternative is a one time license fee, which would incentivize the software to "look shiny", but have no direct motivation for actual usefulness.
 - It's not profit based, so the royalties are not vulnerable to things like "hollywood accounting"

This license is "fire and forget", just slap it on uploaded code and you're done.

If a library with this license includes another library with this license, the percentages add up through the inclusion tree (watch out for this going over 100%).  If you include two libraries, and each of those include the same version of a third one, you only need to pay royalties to the third one once, not once per library that uses it.  This means that each additional library you include in something will progressively cost less as you include more.  Note that you pay royalties to every library in the tree directly, not in a chain of middlemen through the tree.

If someone forks a library with this license, they can't change the original royalty, but they can add another one.  I am imagining pull requests could involve granting rights to modify the new royalty for market reasons given certain legal obligations (eventually).

In the future maybe:

 - Something for Software As A Service, like the Affero GPL.  Because making better websites is good.
 - Explicitly allow static linking, to allow for better optimizations
 - Expand more on the use case of tools such as editors and compilers, to incentivize their development.

----


### The Math, and why it needs to be there

If a project has one contributor (called "A") who values their contribution at 10% of revenue, users of the project don't actually pay 10% of their revenue.  They instead pay

0.1 / (1 + 0.1) = 0.090909...  (9.1%)

This division exists to reflect the fact that using the project increases revenue.

If contributor "B" comes along and adds another 10%, the total royalty becomes

0.2 / (1 + 0.2) = 0.16666...  (16.7%)   rather than 20%.

With 0.1 / (1 + 0.2) = 0.0833333...   (8.3%) paid to each of contributors A and B.


The reason for this is that by the time we get to contributor Z, with 26 different contributors, each adding 10% of value to the original revenue stream, if the royalties were simply added together, the project would cost 260% of revenue.  And despite the project adding a claimed 260% to revenue, the math works out for the project to be completely unusable by anyone that wants to make any sort of profit.

On the other hand, if we use the other math above, the total royalties come out to

2.6 / (1 + 2.6) = 0.72222... (72.2%)

Which is high, but not impossible.  Especially if the project actually increases revenue by 260%, making the business break even.


So, the fractions that each contributor chooses as the value as their contribution is a "nominal royalty", in relation to revenue BEFORE the value of the project is added.

The actual royalty paid is

Sum / (1 + Sum), where "Sum" is the sum of nominal royalties for each contributor

with x / (1 + Sum) paid to contibutor X (who in this case adds x as their nominal royalty fraction).


In the future, it may be necessary to add a multiplier to the Sum that can be adjusted by the project owner for market reasons.

