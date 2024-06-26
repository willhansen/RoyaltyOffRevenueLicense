# About the Royalty Off Revenue License

## Intro

The motivation for this license is that software being source-available and forkable is good, but being $0-to-use is not, because economic incentives get things done.

Whenever a software company wants to make a new software, they can write all the code from scratch (expensive/impossible), lean on the work of volunteers in the form of open source software (potentially unreliable), buy licenses for tools and frameworks (expensive), or rely on software-as-a-service services (expensive / potentially unreliable).  This is not working well.  The systems are too complex for one company to do everything, and volunteers tend to primarily focus on the core moving parts of software, often paying less attention to less interesting, but high value, parts, such as documentation, unit tests, ease of use, and interaction with other programs.  There are exceptions to this, but they are the best of the best, where instead it could be run of the mill.

The core problem is that existing software licenses provide no direct incentives to improve existing software or create software to fill a need.  If I have a cool idea for a software library that could save a lot of people a lot of time just by coding it up and posting it on Github, I can't just slap an existing license on it and "let the cash roll in".  If I find room for improvement in an existing open source library, there is a free-rider scenario where everyone gets just the same benefit no matter who puts in the work.

Generally, there is currently no easy way to take advantage of the specialization and massive economies of scale that software is naturally suited for (software should have ALL of the economies of scale).

## Perspectives we care about

### Open source developers

Open source developers are making tools to fill needs.  They tend to work on their projects in their spare time, rather than for money as a job.  Many would do so full-time if they could.

### Businesses

Businesses want their tools to be easy to use, well tested, documented, and supported.  Also cheap, but sometimes "you have to spend money to make money".

### Personal use

These people tend to have smaller budgets than businesses, and want the software they use to be basically functional.

### Pre-revenue startups

Large overlap in use case with businesses, but with much less budget.

## License goals

### Source-available

Meaning anyone can see the source code, not necessarily being $0-to-use or having no restrictions on use.

If someone can read, compile, and run the code, all on their local machine, they can trust that they know what they're running.  It's well established that open source code is generally more secure than closed source code.

### Anyone can contribute to or fork a project

With open source code, anyone can code up improvements to a library or application.  One of the great strengths of Open Source Software projects is that those people can easily contribute back to the project with a fork or pull request.

Additionally, if a lone project owner starts going "off the rails", the community can fork a project and keep going.

### Modifications to the code must be disclosed

There is a lot of duplicate work done by multiple companies trying to accomplish the same thing.  They all hide their code, and work is wasted.  By forcing disclosure of code modifications, that duplicate work is eliminated.

#### No software-as-a-service loophole for disclosure

Some licenses (like the GPL and LGPL) only require source code to be disclosed if the final binaries are distributed, allowing someone to run the binary on a private server on external data, and not have to disclose a thing.  Other licenses such as the AGPL and SSPL avoid this problem. 

### Easy to include in another project

Another strength of Open Source Software licenses is that having all the conditions of use clearly shown in the license allows potential library users to make a decision ahead of time, and simply include the code if they want to use it.  This allows for massive trees of libraries including libraries including libraries, the abstraction making life easier for everyone.  Needing to negotiate the cost of the license for each use would be time prohibitive for all parties.

A key aspect of being easy to include in a project is keeping the conditions of the license local to the covered code.  Like how the LGPL only requires changes to a covered library to be published, rather than the code of an entire project that includes the library, like the GPL and AGPL.

### Costs money

"But wait", you say, "isn't $0-to-use good?"

"There is no such thing as a free lunch".  If a developer or business isn't getting paid for their work, they have no incentive to make their software useful for money-making applications, no incentive to spend time on the "boring" parts like documentation and tests, and no incentive to keep supporting the project for a long period of time.

The greatest weakness of existing Open Source Software licenses is that, while it is possible for anyone to improve a project themselves, they would need to do so for free.  Those that live by the phrase "if you're good at something, never do it for free" generally don't donate their time to the project.  Work has value.

The least "fun" parts of making a library, such as testing, documentation, and long-term support, are often the most neglected, while also being some of the most valuable.

Also, businesses don't want to hand valuable work to their competitors for free.

#### Cost is proportional to money gained from its use (i.e. royalties)

This provides a direct incentive for software contributors to make software better for businesses.  Beyond just attracting new users (as one-time license fees incentivize) and being just better than the next option (as fixed ongoing license fees incentivize). This directly incentivizes improvements for existing users too.  The more money the users make, the more money the contributors make.  It's win-win.

This also has the benefit of being free for people who don't make money off the use of the library, such as students, hobbyists, and pre-revenue startups.
#### Royalties are proportional to revenue (rather than profit)

Profit can be easily manipulated by tricky accounting (like hollywood accounting).  Revenue is much less ambiguous.

#### The revenue considered for royalties is total revenue, not just the gain in revenue from use of the software

I'm not 100% on this one.  The motivating question here is whether a company can prove that their claimed gain in revenue is correct.  My reasoning is that annual (or perhaps monthly?) total revenue numbers are much easier to get/calculate.

##### Some example cases highlighting potential flaws in this approach: 
Let's say there are several companies using a video editor that is under the license.  All of them gain the same amount of revenue throughout a year:
1. Uses it all the time and makes all their videos with it.  It's a critical part of their workflow.  If the software did not exist, the company would be unable to function, and gain no revenue.
2. Uses it in only 10% of their videos.  Without the software, they wouldn't be able to make those videos.
	- The revenue gained by those videos is easy to see from within the company, but is it possible to prove those numbers to external people? (That's a real question.  I'm no accountant.  If I'm missing something obvious, please let me know)
	- Pays the same amount of royalties as company 1
3. Uses it on all their videos, but it's not critical.  Using it raised their revenue by 10%.
	- Can it be proven that the gain in revenue was caused by using the software, and not a lucky shout-out by a minor celebrity that happened the same week they switched workflows?
	- Pays the same amount of royalties as company 1
4. Uses it on all their videos, and, like business 1, it is a critical part of their workflow, but they only use 10% of the software.  90% of it is completely unused.
	- That part of the editor could potentially be split off into a standalone application with a lower royalty?
	- Pays the same amount of royalties as company 1
5. Uses it on all their videos, like company 1, but they only started using it in the last 10% of the year. For whatever reason, they cannot go back to their old workflow, so the software is now a critical part of their workflow.
	- This suggests that a finer-grained timescale is better, but I don't know how visible those revenue numbers are from outside a company.
	- Pays the same amount of royalties as company 1

#### Royalty distribution between contributors is clearly defined

We're dealing with money, so how that money is going to be distributed needs to be in writing. 

#### Royalty distribution between contributors can change as the codebase changes

People join and leave project teams all the time.  The license needs to account for that.

#### A contributor's share of royalties cannot change without their approval

Someone being able to remove a contributor's share of royalties, without that contributor's input, while the code that contributor wrote is still in use and bringing in royalties, would not be good.

Scenarios where it would probably be fine for a contributor to a project to not get a share of the royalties coming in:
- They agree to it.
- All the code has been rewritten.  Their code is no longer in the project.
	- Using an earlier version of the project, with their code in it, should still give them royalties.
- The version of the project being used is from before that contributor made any contributions.
	- Using a later version of the project, with their code in it, should still give them royalties.

#### Royalty distribution is consistent with sub-project inclusion

Take two cases:
 1. Developer A and developer B each contribute 50% of a project
 2. Case 1 is slightly refactored so developer A has a project that includes a second project made by developer B
Both cases have essentially the same contributions by each developer, and any end user would not be able to tell the difference.  So the royalty distribution should be the same between the two cases.

#### A lone developer can set their royalty percentage to whatever they want

If a developer automates 5% or 95% of a process, the license should be able to accommodate. 

the developer has an incentive to set the royalty percentage correctly, because if it's too high, it's not worth using their software, and if it's too low, they are leaving money on the table.

If they set the royalty to 100% of revenue, no one can gain revenue by using their project.
If they set the royalty to 0% of revenue, the project is effectively just $0-to-use for everyone.

#### Changes to the code and changes to the royalty distribution happen at the same time

To keep things simple, storing the royalty distribution numbers with the code would allow everything to be synced up together.

### Easy to apply to a new project

This license should be "fire and forget".  Just set the price,  slap it on uploaded code, and you're done.


## Consequences of these goals

Let's list out and number the target features for easy reference (TODO: auto-link):

**Goals:**
1. Source-available
2. Anyone can contribute to or fork a project
3. Modifications to the code must be disclosed
	1. No software-as-a-service loophole for disclosure
4. Easy to include in another project
5. Costs money
	1. Cost is proportional to money gained from its use (i.e. royalties)
	2. Royalties are proportional to revenue (rather than profit)
	3. The revenue considered for royalties is total revenue, not just the gain in revenue from use of the software
	4. Royalty distribution between contributors is clearly defined
	5. Royalty distribution between contributors can change as the codebase changes
	6. A contributor's share of royalties cannot change without their approval
	7. Royalty distribution is consistent with sub-project inclusion
	8. A lone developer can set their royalty percentage to whatever they want
	9. Changes to the code and changes to the royalty distribution happen at the same time
6. Easy to apply to a new project
### Royalty distribution table location
Goal 5.4 means the the royalty distribution needs to be written down.  This, combined with 5.9, suggests that a top-level text file in a project directory could work.  Possibly some variety of table or csv with "Name", "Email", and "Fraction of Royalties" columns.

### Adding value to a project, and how that added value is distributed
Goals 5.5 and 5.6 together are tricky.  If a contributor, for example, does 20% of the work, then leaves, never to be heard from again, future additions can't reduce their share of royalties (without their permission or rewriting their code), but additional contributions to the project clearly could be just as valuable.  
If 5 more contributors come along and each add the same amount of value to the project, the math doesn't work out to give all 6 contributors 20% of the royalties, and giving each contributor $\frac{100\%}{6}=16.7\%$ of the royalties lowers the first contributor's share, which is also non-viable.

The solution to this question is to split the royalties six ways equally (as the contribution is equal in this case), but at the same time also raise the overall royalty percentage cost of using the project.

If we track the royalty distributions as shares rather than percentages, adding shares to the project by contributing work can raise the overall royalty percentage proportionally.

For example, if there are 5 contributors with equal shares, and a 7% overall royalty cost,
the royalty distribution table would look like this:

|        name        | shares |
|:------------------:|:------:|
|   Contributor A    |   20   |
|   Contributor B    |   20   |
|   Contributor C    |   20   |
|   Contributor D    |   20   |
|   Contributor E    |   20   |

*Total royalty cost: 7%*   

Another contributor adding the same amount of value to the project would just add another row to the table and raise the total royalty by 20% to 8.4% (from $`\frac{\text{shares after}}{\text{shares before}} = \frac{20*6}{20*5} = \frac{120}{100}= 1.2 \Rightarrow 1.2 * 7\% = 8.4\%`$)

|        name        | shares |
|:------------------:|:------:|
|   Contributor A    |   20   |
|   Contributor B    |   20   |
|   Contributor C    |   20   |
|   Contributor D    |   20   |
|   Contributor E    |   20   |
|   Contributor F    |   20   |

*Total royalty cost  8.4%* 

While this should leave all contributors happy, as they were each getting $20/100 * 7\% = 1.4\%$ of revenue as royalties before, and  $20/120 * 8.4\% = 1.4\%$ of revenue as royalties after, there is clearly an effect on the user of the licensed software, who sees their cost go up 20%.

This is justified by:
1. The value of the software has (allegedly) gone up 20%.  If that added value increases the user's revenue by more than the 1.4% price increase, everyone should be happy. 
2. If the value to that user has not increased accordingly (maybe they just don't need that new feature), the user can simply stay with the older version with the older cost.
3. The user (or anyone, really) can fork the project with the new feature cut out, and undercut the price of the main project (assuming there are others who also don't need/want that feature).

There is still a problem, though.  The royalty percentage does not have a cap.  The $\frac{\text{shares after}}{\text{shares before}}$ ratio can become arbitrarily large, and cause the total royalty cost to grow to and beyond 100%.  The end user can be squeezed out, despite doing work to bring in revenue themselves.

If we start here:

|        name        | shares |
|:------------------:|:------:|
|   Contributor A    |   20   |
|   Contributor B    |   20   |
|   Contributor C    |   20   |
|   Contributor D    |   20   |
|   Contributor E    |   20   |

*Total royalty cost: 7%*   

And add "just" sixty-seven more equal contributors:

|      name       | shares |
|:---------------:|:------:|
|  Contributor A  |   20   |
|  Contributor B  |   20   |
|  Contributor C  |   20   |
|  Contributor D  |   20   |
|  Contributor E  |   20   |
|       ...       |  ...   |
| Contributor #72 |   20   |

*Total royalty cost: 100.8%*

$`\frac{\text{shares after}}{\text{shares before}} = \frac{20*72}{20*5} = \frac{1440}{100}= 14.4 \Rightarrow 14.4 * 7\% = 100.8\%`$

Using the project costs more than 100% of revenue, and the end user gets no revenue themselves, even needing to pay more money than the revenue they bring in.  This doesn't seem right, as even if the value of the software has gone up by a factor of 14, the end user is still  doing valuable work they should be getting money for.

So we add a line of shares for them:

$`\text{end user shares} = \frac{\text{sum of contributor shares}}{\text{target royalty cost}} * (100\% - \text{target royalty cost}) = \frac{100}{7\%} * 93\% = 1328.5714`$

Round to 1329 shares.  Note that the fact that this is rounded means all calculations must be done from the number of shares.  The final "total royalty cost" is imprecise (6.997901...% rather than 7%).

|     name      | shares |
|:-------------:|:------:|
| Contributor A |   20   |
| Contributor B |   20   |
| Contributor C |   20   |
| Contributor D |   20   |
| Contributor E |   20   |
|               |        |
|   End User    |  1329  |

*Total royalty cost: ~7%*   

>[!note]
>The "End User" name is not replaced with an actual name when this table is placed in a real project.  It is a stand-in for "Whoever uses this project under this license".

Then when we add a new contributor, the formula for total royalty cost becomes $`\frac{\text{sum of contributor shares}}{\text{sum of all shares}} = \frac{20*72}{20*72 + 1329} = \frac{1440}{2769}= {\sim}0.52 = {\sim}52\%`$

|      name       | shares |
|:---------------:|:------:|
|  Contributor A  |   20   |
|  Contributor B  |   20   |
|  Contributor C  |   20   |
|  Contributor D  |   20   |
|       ...       |  ...   |
| Contributor #72 |   20   |
|                 |        |
|    End User     | 1328.6 |

*Total royalty cost: ~52%*

With each contributor individually getting $`\frac{\text{contributor shares}}{\text{sum of all shares}} = \frac{20}{2769} = {\sim}0.0072 = {\sim}0.72\%`$ of revenue

At this point, you may notice that each contributor's fraction of revenue just went down.  This makes sense if you consider the revenue before the contributions and after the contributions as two different values $R_1$ and $R_2$, with $R_2$ being larger due to the value increase of the project allowing the end user to bring in more revenue.  

Everything is fine if an early contributor is bringing in the same amount of money before and after the later contributions. (Again note that these calculations must be done with the numbers of shares, as the percentage values are approximate)

$`\frac{\text{contributor's shares at start}}{\text{total shares at start}} * R_1 = \frac{\text{contributor's shares at end}}{\text{total shares at end}} * R_2 \\\Rightarrow \frac{\cancel{20} * 2769}{\cancel{20} * 1429} * R_1 = R_2 \\\Rightarrow \boxed{ \frac{R_2}{R_1} = {\sim}1.94}`$

The same goes for the end user:

$`\frac{\text{end user's shares at start}}{\text{total shares at start}} * R_1 = \frac{\text{end user's shares at end}}{\text{total shares at end}} * R_2 \\\Rightarrow \frac{\cancel{1329} * 2769}{\cancel{1329} * 1429} * R_1 = R_2 \\\Rightarrow \boxed{ \frac{R_2}{R_1} = {\sim}1.94}`$

If the contributions make the revenue go up by a factor of ~1.94, the math works out.

If shares accurately represent value, then the $\frac{\text{shares after}}{\text{shares before}}$ ratio should also reflect the same rise in revenue.  We get $\frac{\text{shares after}}{\text{shares before}} = \frac{2769}{1429} = \boxed{{\sim}1.94}$, so no one is seeing any change in income due to later contributions (so long as each next contributor gets the appropriate number of shares for the value of their work).

At this point, the question becomes: "If neither the original contributors nor the end users are getting any more money, why would they accept this new contribution?".  
1) The contributor could take less shares themselves as incentive to merge their contribution.  (The exact value of their contribution is likely fuzzy in any case.  User interfaces or documentation being classic examples.)
2) The contributor can simply fork the project at any time. If they believe their contribution will add more value than they can negotiate in shares, this could be a good route.


### Forks, includes, and merge requests

These are all aspects of the same thing as far as the license is concerned (assuming both the base and sub-projects are under this license).  
- A fork is putting a code change and associated royalty addition on top of a base project
- A merge request is presenting an offer to the base project.  "These code changes, for this royalty addition".
- Including a sub-project (eg a library) in a base project is the base project accepting the offer that the sub-project made to everyone by being published.  The inclusion similarly changes code, and adds an associated royalty.

Goal 5.7 means that if there's a sub-project with x% of revenue as the cost, that percentage must map to a number of shares of a base project including it.

This is good because it allows us to treat every sub-project inclusion as just another contribution, with contributors to the sub-project getting shares of the main project.  The end user does not need to know the difference, and royalty table in the main project is the only one they need to worry about.

Now all that's left is the actual mapping of shares from the sub-project to the main project. 
For example, let's say there are two existing contributors to a project, and they want to include a sub-project

**Main project:**

|     name      | shares |
|:-------------:|:------:|
| Contributor A |   20   |
| Contributor B |   20   |
|               |        |
|   End User    | 60       |

*Total royalty cost: 40%*


**Sub-project:**

|     name      | shares |
|:-------------:|:------:|
| Contributor C |   8    |
| Contributor D |   2    |
|               |        |
|   End User    | 90       |

*Total royalty cost: 10%* 

Let's put these in one table for convenience:

|     name      | main project shares | sub-project shares |
|:-------------:|:-------------------:|:------------------:|
| Contributor A |         20          |                    |
| Contributor B |         20          |                    |
| Contributor C |                     |         8          |
| Contributor D |                     |         2          |
|               |                     |                    |
|   End User    |         60          |         90         |


Before these tables can be combined properly, we need to make the end user shares match by multiplying each column by a constant.

| name | main project shares | sub-project shares |
| :--: | :--: | :--: |
| Contributor A | 60 |  |
| Contributor B | 60 |  |
| Contributor C |  | 16 |
| Contributor D |  | 4 |
|  |  |  |
| End User | 180 | 180 |

| name | main project shares |
| :--: | :--: |
| Contributor A | 60 |
| Contributor B | 60 |
| Contributor C | 16 |
| Contributor D | 4 |
|  |  |
| End User | 180 |

*Total royalty cost:* $`\frac{140}{320}={\sim}44\%`$

## Current licensing options

There are really two main questions to consider for each of these options:
  1. Would someone use a library under this license?
  2. Would someone apply this license to code they are writing?

### GPL/LGPL/AGPL

Free to use, and you need to re-contribute changes made to the code.  This is bad for business owners to apply to their code, because then anyone can use the code without giving them money for it.  LGPL licensed libraries are good to use, because they're free and the license is limited to the library, but the GPL and AGPL are more virulent, and would affect the rest of the codebase.

### Creative Commons (non-commercial)

Totally excludes commercial use.  Unthinkable for businesses.

### Permissive licenses (BSD, MIT, Apache, etc.)

Free to use, and you can hide any modifications to the code.  This is the kind of license businesses like to see in the libraries they use, but the lack of benefits for the library developer or forced recontribution means the quality is often left wanting.

### Dual licensing

There are several forms:

* An open source license unless you pay for a proprietary license
* Proprietary until some date, then becomes open source licensed automatically
* Open source license for non-commercial use, otherwise you need a proprietary license.

These options offer a path to monetization for library developers, and share code, but they all also require the project to have a proprietary license, which is more overhead for developers.

There is a lot of freedom in defining the proprietary license, which can be good for businesses, but is more overhead for lone developers.

### Software as a service

This is one of the more business-friendly ways of selling software.  It works, but it's not a good solution if you care about latency, security, or have an inconsistent internet connection.

---

## Proposed solution: The Royalty Off Revenue license

Exactly like its name implies, the Royalty Off Revenue license allows anyone to use the licensed software as long as they give the developer a percentage of their revenue.

It also defines how contributors to a project under the license can add their own royalties, offering an incentive to contribute.

Code under the license that is modified must be disclosed.

The percentage of revenue to be paid is defined by the developer within the license, making it easy for potential users to make decisions.

Overall, the license is intended to be largely similar to the LGPL, with the exception of the royalties.  Ideally implemented as a modifier to a given existing license, similar to a dual license.

Something along the lines of:
"This license is the LGPL license, but with the additional condition that you need to pay a percentage of your total annual revenue to the contributors of this project with as defined in the included `royalty_distribution_table.csv` file."


> [!Info] Disclaimer 
> I am not a lawyer.

### The specific behavior we want out of the license:

- If someone modifies your code, they need to make that modified code available
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
  - $0-to-use
  - No revenue ==> no royalty payment
- If all creators of a piece of software don't add required royalties to the license, this license should be more or less equivalent to the LGPL
- If all users of a piece of software don't get any revenue, this license should be more or less equivalent to the LGPL
- Each contributor to a project should be able to lower their own previously added royalty if they want to.
- Each contributor to a project should be able to raise their own previously added royalty if they want to, though users will still be able to use the lower price from the previous version, and a project owner may not accept this change, requiring a fork.

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
  - Note that User A can easily make Thing B not contain ROR-licensed software at time of sale, but download it on first startup

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
  - Simple case (1) applies to User C. ==>  User C pays royalty for revenue gained by using Thing B (both 0 in this case)

User A makes Thing B, *applies* the ROR-license to it, and *sells* it to User C, who then *gains revenue by using it*
  - Simple case (4) applies to User A. ==>  No royalty payment from User A
  - Simple case (1) applies to User C. ==>  User C pays royalty for revenue gained by using Thing B

User A makes Thing B *using* ROR-licensed software. Thing B also *contains* ROR-licensed software, and User A *applies* additional royalties to it (through the ROR license's mechanism for doing so).  User A then *sells* Thing B to User C, and User C *gains revenue* by *using* Thing B.
  - Simple cases (2), (3), and (4) apply to the initial sale of Thing B. ==> User A pays royalties off the sale revenue for the *use* of ROR-licensed software in the creation of Thing B.
  - Simple case (1) applies to User C. ==> User C pays royalties for revenue gained by using Thing B. Specifically to User A for the applied royalties, and to whoever gains royalties for the ROR-licensed software contained in Thing B

## Frequently Asked Questions:

### Q. If you're restricting the freedom of users of the licensed software, it's not really Open Source Software™, is it?

A. The problem we're trying to solve is that too many businesses are taking advantage of "the freedom to take your work, make buckets of money off it, and not give you a cent".  Restricting that freedom is the only solution to that problem I've come across.

### Q. If we inform businesses that they need to voluntarily contribute to our open source projects to maintain the system for their own long-term benefit, surely they'll do the right thing?

A. How's that strategy been working out with taxes / global warming / this exact thing?

## Next steps:

1. Get feedback on this document
2. Create a rough draft of the license itself
  - As I am not a lawyer, I can only assume that if I write it myself, it will be wrong
