# The Royalty Off Revenue License


The motivation for this license is that "freedom free" is good, but "beer free" is not, because economic incentives get things done.

Volunteers tend to primarily focus on the core moving parts of software, often paying less attention to less interesting, but high value, parts, such as documentation, unit tests, ease of use, and interaction with other programs.  There are exceptions to this, but they are the best of the best, where instead they could be run of the mill.

The core problem is that existing software licenses provide no direct incentives to improve existing software or create software to fill a need.  If I have a cool idea for a software library that could save a lot of people a lot of time just by coding it up and posting it on Github, I can't simply slap an existing license on it and "let the cash roll in".  If I find room for improvement in an existing open source library, there is a Free Rider Problem, where everyone gets just the same benefit no matter who puts in the work.

Generally, there is currently no easy way to take advantage of the specialization and massive economies of scale that software is naturally suited for (software should have ALL of the economies of scale).

----

Percentage of revenue means:

 - It's effectively free for students, hobbyists, researchers, and pre-revenue startups.
 - There is a direct financial incentive for the software creator to want the software user to make more money.  The alternative is a one time license fee, which would incentivize the software to "look shiny", but have no direct motivation for actual usefulness.
 - It's not "profit" based, so the royalties are not vulnerable to arbitrary expenses and "hollywood accounting"

This license should be "fire and forget".  Just set the price, slap it on uploaded code, and you're done.

If a library with this license includes another library with this license, the percentages add up through the inclusion tree (watch out for this going over 100%).  If you include two libraries, and each of those include the same version of a third one, you only need to pay royalties to the third one once, not once per library that uses it.  This means that each additional library you include in something will progressively cost less as you include more.  Note that you pay royalties to every library in the tree directly, not in a chain of middlemen through the tree.

If someone forks a library with this license, they can't change the original royalty, but they can add another one.  I am imagining pull requests could involve granting rights to modify the new royalty for market reasons given certain legal obligations (eventually).

TODO:
 - Something for Software As A Service, like the Affero GPL.  Because making better websites is good.
 - Explicitly allow static linking, to allow for better optimizations
 - Expand more on the use case of tools such as editors and compilers, to incentivize their development.


## Perspectives we care about

### Library developers

Library developers are making tools to fill needs.  They tend to work on their projects in their spare time, rather than for money as a job.

### Businesses

Businesses want their tools to be easy to use as well as well tested, documented, and supported.  Also cheap, but sometimes you have to spend money to make money.

### Personal use / Pre-revenue startups / Students / Academic Researchers

These people tend to have small budgets, and want their software usable and free (in terms of money).

---

## Desirable license features

### Open source

By which, we mean anyone can see the source code, not necessarily free to use.  Distinct from the fully capitalized "Open Source", which comes with additional baggage.

If someone can read, compile, and run the code, all on their local machine, they can trust that they know what they're running.  It's well established that open source code is generally more secure than closed source code.

### Anyone can contribute

With open source code, anyone can code up improvements to a library or application.  One of the great strengths of Free Software projects is that those people can easily contribute back to the project with a fork or pull request, even without the permission of the original developer.

### Modifications to the code must be disclosed

There is a lot of duplicated work done by multiple companies trying to accomplish the same thing.  They all hide their code, and the same work is done multiple times independently.  By forcing disclosure of code modifications, that duplicate work is eliminated.

On the other hand, when that disclosed code can be used for free by competitors, a free rider problem arises, where everyone but the first person to put in the work gets all the benefit for free.  There needs to be a way to put a price tag on the disclosed code, so both duplicate work and a free rider problem can be avoided.

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

(As an aside, an ALGPL license apparently does not exist, but should)

### Dual licensing

GPL unless you pay for a proprietary license, this option offers a path to monetization for library developers and is free if you don't mind the GPL license, but typically allows proprietary license holders to hide their code and requires negotiation for each license.

There is a lot of freedom in defining the proprietary license, which can be good for businesses, but is more overhead for lone developers.

### Creative Commons (non-commercial)

Totally excludes commercial use.  Unthinkable for businesses.

### Permissive licenses (MIT, Apache 2.0, etc.)

Free to use, and you can hide any modifications to the code.  This is the kind of license businesses like to see in the libraries they use, but the lack of benefits for the library developer or forced recontribution of modified code means the quality is often left wanting.


### Software as a service

This is one of the more business-friendly ways of selling software.  It works, but it's not a good solution if you care about latency, security, or have an inconsistent internet connection.

---

## Proposed solution: The Royalty Off Revenue license

Exactly like its name implies, the Royalty Off Revenue license allows anyone to use the licensed software as long as they give the developer a percentage of the revenue earned from its use.

It also defines how contributors to a project under the license can add their own royalties, offering an incentive to contribute (explained in [Appendix A](#appendix-a-the-math)).

Code under the license that is modified must be disclosed.

The percentage of revenue to be paid is defined by the developer within the license, making it easy for potential users to make decisions.

Overall, the license is intended to be largely similar to the LGPL, with the exception of the royalties.

The specific behavior we want out of the license:

- If someone modifies your code and then distributes it, or runs it as part of a service, they need to publish that modified code (similar to the LGPL, or a hypothetical ALGPL)
- If someone makes money by using or selling your code, they need to give you a fraction of their revenue, with that fraction of revenue being defined by the developer within an included configuration file 
  - Someone runs your code to gain revenue -> they pay you a royalty based on that revenue
    - End user buys application that uses your code, and uses that application to make money -> pay royalty
    - Someone buys a robot that is running the library somewhere inside, and makes money by using it -> pay royalty
  - Someone sells your code to gain revenue -> they pay you a royalty based on that revenue
- If someone modifies your code, they may add their own royalties on top of the existing ones, because their work has value too
  - They may NOT remove existing royalties
- If someone runs or distributes your code and does not gain revenue from it, they don't owe anything.
- If all creators of a piece of software don't add required royalties to the license, this license should be more or less equivalent to the LGPL
- If all users of a piece of software don't get any revenue, this license should be more or less equivalent to a hypothetical ALGPL
- Each contributor to a project should be able to LOWER their own previously added royalty if they want to.
- Each contributor to a project should be able to RAISE their own previously added royalty if they want to, though users will still be able to use the lower price from previously released versions

TL;DR: Like a hypothetical ALGPL, but you have to pay a percentage of your revenue to use or sell licensed software.

---

----

The goals of this license are as follows.  If the legalities of the license do not line up with these goals, the next version of the license should be changed to line up with these goals:

 - If someone modifies your code, they need to make that modified code available (similar to the lgpl)
 - If someone makes money by using or selling your code, they need to give you a fraction of their revenue
    - Running your code to make money -> pay royalty
    - Selling an application that uses your code -> pay royalty on sale revenue
    - End user buys application that uses your code, and uses that application to make money -> pay royalty
        - (To prevent a shell company selling expensive software for 1$ to the "real" user, thus gaming the royalty system.  Or would that just be regularly illegal, so we don't have to cover it here?)
        - (This also incentivizes tools such as editors and compilers)
    - Someone buys a robot that is running the library somewhere inside, and makes money by using it -> pay royalty
        - (This one is a bit iffier than the others, but I think it's the same case as the point above, the robot being essentially the same as a pc running an application, and the royalties being for the use of the software rather than for the sale of the hardware.)
 - If someone modifies your code, they may add their own royalties on top of the existing ones
    - (As an incentive for them to make your code better)
 - If someone modifies your code, they may NOT remove existing royalties
 - If someone modifies your code, adding royalties is the ONLY change they may make to the license
 - The code needs to be "beer free" for people who don't use the software to make money
 - If all creators of a piece of software don't add required royalties to the license, this license should be more or less equivalent to the lgpl
 - If all users of a piece of software don't get any revenue, this license should be more or less equivalent to the lgpl
 - The creator/owner of a piece of software should be able to lower the required royalties if they want to.
 - The creator/owner of a piece of software should be able to raise the required royalties if they want to, but users could still use older versions with the older and lower price.


## How royalties can change with additional contributions

### Why do they need to change?

Allowing additional royalties for contributions to a project motivates those contributions.
Especially the low-fun, high-value contributions such as documentation, bug fixes, and unit tests.

### Why even limit it at all?

There need to be limits to prevent someone from fixing a typo and changing the royalty distribution to give them all the money.
Such a change would probably not be accepted to be merged back into the main project, but even having forks of a project with such changes would not be ideal.

### A well-defined process for adding royalties for additional contribution to a project

#### Adding royalties to a project should not reduce the royalties for existing work done

Adding a feature to a project does not reduce the value of existing features.  The process for adding royalties with a contribution should reflect this.





### The Math, and why it needs to be there

Scenario: Developers A and B make a piece of software, and put it under the Royalty Off Revenue license.  The user then takes that software and gains x$ of revenue through its use.

The royalties owed on that revenue are described with a share distribution such as the following table.

who         |  shares
-----------------------
Developer A |   10
Developer B |   10
User        |  100
-----------------------
total       |  120


User has 100 shares, which represent the revenue after royalties are paid.
The total shares are 120, which represent the total revenue.
Developers A and B each have 10 shares, signifying that they split the royalties equally.

The actual payout to each is simply: (shares / total shares) * 100% of total revenue

developer A:   10/120 * 100% = 8.333333%
developer B:   10/120 * 100% = 8.333333%
User:         100/120 * 100% = 83.33333%


who         |  percent of revenue 
-----------------------------------
Developer A |   8.33% 
Developer B |   8.33%
User        |  83.33%
-----------------------------------
total       | 100.00%

So the royalty percentage for using the software is 16.66%


If Developer C comes along and contributes to the project, and allocates themselves one share, that share is created, not taken from someone else.  That added share represents the value added to the project by Developer C's contribution.

who         |  shares
-----------------------
Developer A |   10
Developer B |   10
Developer C |    1
User        |  100
-----------------------
total       |  121


The percentage of revenue table becomes the following:


who         |  percent of revenue 
-----------------------------------
Developer A |   8.264% 
Developer B |   8.264%
Developer C |   0.826%
User        |  82.646%   (extra 0.001%)
-----------------------------------
total       | 100.000%


While it initially appears as though the money gained by Developers A and B has dropped, this is countered by the idea that Developer C's contribution has improved the software by one share's worth of value, and thus the end user should gain that much more revenue.

Additionally, the royalty for using the software has risen to 17.35% of revenue, because it is worth more now.


If Developers A and B do not agree that Developer C's contribution adds that much value to the software, they are not required to accept a pull request.  However, Developer C can still release a fork of the software with the updated revenue distribution table, and the User may opt to use that fork if they agree with Developer C's value assessment.

Note that while Developer C can allocate themselves new shares, they cannot remove shares from other developers or the end user.






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


If you receive revenue by using or distributing the library, you must pay a fraction of that revenue as a royalty to parties as described in section 14.


### How much to pay to who


For every row in this table, you must pay a fraction of revenue as defined in the "Actual fraction of revenue" column to the party defined in that row.

To                               |  Contact information               | Nominal fraction of revenue | Actual fraction of revenue
---------------------------------|------------------------------------|-----------------------------|----------------------------
Example Mcnobody | ExampleMcnobody@notawebsite.com |  0.000| 0.000
                                 |                                    | NOMINAL SUM: 0.00       | ACTUAL SUM: 0.00

The "Nominal fraction of revenue" column values are to be chosen by the party adding each row.

The "NOMINAL SUM" value is the sum of the "Nominal fraction of revenue" column and must be recalculated each time a row is added or modified, BEFORE the "Actual fraction of revenue" column is recalculated.

The values in the "Actual fraction of revenue" column are to be calculated by the formula (x / (1 + NOMINAL SUM)), where "x" is the value in the "Nominal fraction of revenue" column in the same row. This entire column must be recalculated each time a row is added or modified.

The "ACTUAL SUM" value is the sum of the "Actual fraction of revenue" column and must be recalculated each time a row is added or modified, AFTER the "Actual fraction of revenue" column is recalculated.


