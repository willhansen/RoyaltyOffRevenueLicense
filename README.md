# The Royalty Off Revenue License


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

#### Including a library with royalties into a project with royalties should work out the same as if that library and royalties were simply added directly to the project

The contributed value is the same in both cases, so the royalty distributions should be the same.

