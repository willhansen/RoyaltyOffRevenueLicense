# ROYALTY OFF REVENUE LICENSE

Version 1, 14 July 2018

Copyright © 2019 William Robert Sadler Hansen

Everyone is permitted to copy and distribute verbatim copies of this license document, but changing it is not allowed.

## VERSION SPECIFIC PREAMBLE

THE GRAND RELEASE!

## PREAMBLE

The motivation for this license is that "freedom free" is good, but "beer free" is not, because economic incentives get things done.

Whenever a robotics company tries to make a robot, they can write all the code from scratch, or lean on the work of volunteers in the form of open source software.  This is not working well.  The systems are too complex for one company to do everything, and volunteers tend to primarily focus on the core moving parts of software, often paying less attention to less interesting, but high value, parts, such as documentation, unit tests, ease of use, and interaction with other programs.  There are exceptions to this, but they are the best of the best, where instead it could be run of the mill.

The core problem is that existing software licenses provide no direct incentives to improve existing software or create software to fill a need.  If I have a cool idea for a software library that could save a lot of people a lot of time just by coding it up and posting it on Github, I can't just slap an existing license on it and "let the cash roll in".  If I find room for improvement in an existing open source library, there is a tragedy of the commons scenario where everyone gets just the same benefit no matter who puts in the work.

Generally, there is currently no easy way to take advantage of the specialization and massive economies of scale that software is naturally suited for (software should have ALL of the economies of scale).

----

The basic idea here is that I took the LGPL V2.1 and more or less slapped a term on it that essentially says "If you use this software to make money, you owe the creator x% off the revenue".

Percentage of revenue means:

 - It's effectively free for students, researchers, and pre-revenue startups.
 - There is a direct financial incentive for the software creator to want the software user to make more money.  The alternative is a one time license fee, which would incentivize the software to "look shiny", but have no direct motivation for actual usefulness.
 - It's not "profit" based, so the royalties are not vulnerable to arbitrary expenses and "hollywood accounting"

This license is "fire and forget", just slap it on uploaded code and you're done.

If a library with this license includes another library with this license, the percentages add up through the inclusion tree (watch out for this going over 100%).  If you include two libraries, and each of those include the same version of a third one, you only need to pay royalties to the third one once, not once per library that uses it.  This means that each additional library you include in something will progressively cost less as you include more.  Note that you pay royalties to every library in the tree directly, not in a chain of middlemen through the tree.

If someone forks a library with this license, they can't change the original royalty, but they can add another one.  I am imagining pull requests could involve granting rights to modify the new royalty for market reasons given certain legal obligations (eventually).

In the future maybe:

 - Something for Software As A Service, like the Affero GPL.  Because making better websites is good.
 - Explicitly allow static linking, to allow for better optimizations
 - Expand more on the use case of tools such as editors and compilers, to incentivize their development.

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

---

The precise terms and conditions for copying, distribution and modification follow. Pay close attention to the difference between a "work based on the library" and a "work that uses the library". The former contains code derived from the library, whereas the latter must be combined with the library in order to run.

# TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION, MODIFICATION, AND USE

## 0.

This License Agreement applies to any software library or other program which contains a notice placed by the copyright holder or other authorized party saying it may be distributed under the terms of this Royalty Off Revenue (also called "this License"). Each licensee is addressed as "you".

A "library" means a collection of software functions and/or data prepared so as to be conveniently linked with application programs (which use some of those functions and data) to form executables.

The "Library", below, refers to any such software library or work which has been distributed under these terms. A "work based on the Library" means either the Library or any derivative work under copyright law: that is to say, a work containing the Library or a portion of it, either verbatim or with modifications and/or translated straightforwardly into another language. (Hereinafter, translation is included without limitation in the term "modification".)

"Source code" for a work means the preferred form of the work for making modifications to it. For a library, complete source code means all the source code for all modules it contains, plus any associated interface definition files, plus the scripts used to control compilation and installation of the library.

## 1.

You may copy and distribute verbatim copies of the Library's complete source code as you receive it, in any medium, provided that you conspicuously and appropriately publish on each copy an appropriate copyright notice and disclaimer of warranty; keep intact all the notices that refer to this License and to the absence of any warranty; and distribute a copy of this License along with the Library.

You may charge a fee for the physical act of transferring a copy, and you may at your option offer warranty protection in exchange for a fee.

## 2.

 You may modify your copy or copies of the Library or any portion of it, thus forming a work based on the Library, and copy and distribute such modifications or work under the terms of Section 1 above, provided that you also meet all of these conditions:

 - a) The modified work must itself be a software library.
 - b) You must cause the files modified to carry prominent notices stating that you changed the files and the date of any change.
 - c) You must cause the whole of the work to be licensed at no charge to all third parties under the terms of this License.
 - d) If a facility in the modified Library refers to a function or a table of data to be supplied by an application program that uses the facility, other than as an argument passed when the facility is invoked, then you must make a good faith effort to ensure that, in the event an application does not supply such function or table, the facility still operates, and performs whatever part of its purpose remains meaningful.

    (For example, a function in a library to compute square roots has a purpose that is entirely well-defined independent of the application. Therefore, Subsection 2d requires that any application-supplied function or table used by this function must be optional: if the application does not supply it, the square root function must still compute square roots.)

These requirements apply to the modified work as a whole. If identifiable sections of that work are not derived from the Library, and can be reasonably considered independent and separate works in themselves, then this License, and its terms, do not apply to those sections when you distribute them as separate works. But when you distribute the same sections as part of a whole which is a work based on the Library, the distribution of the whole must be on the terms of this License, whose permissions for other licensees extend to the entire whole, and thus to each and every part regardless of who wrote it.

Thus, it is not the intent of this section to claim rights or contest your rights to work written entirely by you; rather, the intent is to exercise the right to control the distribution of derivative or collective works based on the Library.

In addition, mere aggregation of another work not based on the Library with the Library (or with a work based on the Library) on a volume of a storage or distribution medium does not bring the other work under the scope of this License.

You may alter this license by adding rows to the royalty table in section 14, but you may not remove or modify existing lines.

## 4.

 You may copy and distribute the Library (or a portion or derivative of it, under Section 2) in object code or executable form under the terms of Sections 1 and 2 above provided that you accompany it with the complete corresponding machine-readable source code, which must be distributed under the terms of Sections 1 and 2 above on a medium customarily used for software interchange.

If distribution of object code is made by offering access to copy from a designated place, then offering equivalent access to copy the source code from the same place satisfies the requirement to distribute the source code, even though third parties are not compelled to copy the source along with the object code.

## 5.

 A program that contains no derivative of any portion of the Library, but is designed to work with the Library by being compiled or linked with it, is called a "work that uses the Library". Such a work, in isolation, is not a derivative work of the Library, and therefore falls outside the scope of this License.

However, linking a "work that uses the Library" with the Library creates an executable that is a derivative of the Library (because it contains portions of the Library), rather than a "work that uses the library". The executable is therefore covered by this License. Section 6 states terms for distribution of such executables.

When a "work that uses the Library" uses material from a header file that is part of the Library, the object code for the work may be a derivative work of the Library even though the source code is not. Whether this is true is especially significant if the work can be linked without the Library, or if the work is itself a library. The threshold for this to be true is not precisely defined by law.

If such an object file uses only numerical parameters, data structure layouts and accessors, and small macros and small inline functions (ten lines or less in length), then the use of the object file is unrestricted, regardless of whether it is legally a derivative work. (Executables containing this object code plus portions of the Library will still fall under Section 6.)

Otherwise, if the work is a derivative of the Library, you may distribute the object code for the work under the terms of Section 6. Any executables containing that work also fall under Section 6, whether or not they are linked directly with the Library itself.

## 6.

As an exception to the Sections above, you may also combine or link a "work that uses the Library" with the Library to produce a work containing portions of the Library, and distribute that work under terms of your choice, provided that the terms permit modification of the work for the customer's own use and reverse engineering for debugging such modifications.

You must give prominent notice with each copy of the work that the Library is used in it and that the Library and its use are covered by this License. You must supply a copy of this License. If the work during execution displays copyright notices, you must include the copyright notice for the Library among them, as well as a reference directing the user to the copy of this License. Also, you must do one of these things:

- a) Accompany the work with the complete corresponding machine-readable source code for the Library including whatever changes were used in the work (which must be distributed under Sections 1 and 2 above); and, if the work is an executable linked with the Library, with the complete machine-readable "work that uses the Library", as object code and/or source code, so that the user can modify the Library and then relink to produce a modified executable containing the modified Library. (It is understood that the user who changes the contents of definitions files in the Library will not necessarily be able to recompile the application to use the modified definitions.)
- b) Use a suitable shared library mechanism for linking with the Library. A suitable mechanism is one that (1) uses at run time a copy of the library already present on the user's computer system, rather than copying library functions into the executable, and (2) will operate properly with a modified version of the library, if the user installs one, as long as the modified version is interface-compatible with the version that the work was made with.
- c) Accompany the work with a written offer, valid for at least three years, to give the same user the materials specified in Subsection 6a, above, for a charge no more than the cost of performing this distribution.
- d) If distribution of the work is made by offering access to copy from a designated place, offer equivalent access to copy the above specified materials from the same place.
- e) Verify that the user has already received a copy of these materials or that you have already sent this user a copy.

For an executable, the required form of the "work that uses the Library" must include any data and utility programs needed for reproducing the executable from it. However, as a special exception, the materials to be distributed need not include anything that is normally distributed (in either source or binary form) with the major components (compiler, kernel, and so on) of the operating system on which the executable runs, unless that component itself accompanies the executable.

It may happen that this requirement contradicts the license restrictions of other proprietary libraries that do not normally accompany the operating system. Such a contradiction means you cannot use both them and the Library together in an executable that you distribute.

## 7.

You may place library facilities that are a work based on the Library side-by-side in a single library together with other library facilities not covered by this License, and distribute such a combined library, provided that the separate distribution of the work based on the Library and of the other library facilities is otherwise permitted, and provided that you do these two things:

- a) Accompany the combined library with a copy of the same work based on the Library, uncombined with any other library facilities. This must be distributed under the terms of the Sections above.
- b) Give prominent notice with the combined library of the fact that part of it is a work based on the Library, and explaining where to find the accompanying uncombined form of the same work.

## 8.

You may not copy, modify, sublicense, link with, or distribute the Library except as expressly provided under this License. Any attempt otherwise to copy, modify, sublicense, link with, or distribute the Library is void, and will automatically terminate your rights under this License. However, parties who have received copies, or rights, from you under this License will not have their licenses terminated so long as such parties remain in full compliance.

## 9.

You are not required to accept this License, since you have not signed it. However, nothing else grants you permission to modify or distribute the Library or its derivative works. These actions are prohibited by law if you do not accept this License. Therefore, by modifying or distributing the Library (or any work based on the Library), you indicate your acceptance of this License to do so, and all its terms and conditions for copying, distributing or modifying the Library or works based on it.

## 10.

 Each time you redistribute the Library (or any work based on the Library), the recipient automatically receives a license from the original licensor to copy, distribute, link with or modify the Library subject to these terms and conditions. You may not impose any further restrictions on the recipients' exercise of the rights granted herein. You are not responsible for enforcing compliance by third parties with this License.

## 11.

If, as a consequence of a court judgment or allegation of patent infringement or for any other reason (not limited to patent issues), conditions are imposed on you (whether by court order, agreement or otherwise) that contradict the conditions of this License, they do not excuse you from the conditions of this License. If you cannot distribute so as to satisfy simultaneously your obligations under this License and any other pertinent obligations, then as a consequence you may not distribute the Library at all. For example, if a patent license would not permit royalty-free redistribution of the Library by all those who receive copies directly or indirectly through you, then the only way you could satisfy both it and this License would be to refrain entirely from distribution of the Library.

If any portion of this section is held invalid or unenforceable under any particular circumstance, the balance of the section is intended to apply, and the section as a whole is intended to apply in other circumstances.

It is not the purpose of this section to induce you to infringe any patents or other property right claims or to contest validity of any such claims; this section has the sole purpose of protecting the integrity of the free software distribution system which is implemented by public license practices. Many people have made generous contributions to the wide range of software distributed through that system in reliance on consistent application of that system; it is up to the author/donor to decide if he or she is willing to distribute software through any other system and a licensee cannot impose that choice.

This section is intended to make thoroughly clear what is believed to be a consequence of the rest of this License.

## 12.

If the distribution and/or use of the Library is restricted in certain countries either by patents or by copyrighted interfaces, the original copyright holder who places the Library under this License may add an explicit geographical distribution limitation excluding those countries, so that distribution is permitted only in or among countries not thus excluded. In such case, this License incorporates the limitation as if written in the body of this License.

## 13.

If you receive revenue by using or distributing the library, you must pay a fraction of that revenue as a royalty to parties as described in section 14.

## 14.

### How much to pay to who

If there is exactly one party described in this table (the one to "William Robert Sadler Hansen"), you may disregard it and pay no royalties.

For every row in this table, you must pay a fraction of revenue as defined in the "Actual fraction of revenue" column to the party defined in that row.

To                               |  Contact information               | Nominal fraction of revenue | Actual fraction of revenue
---------------------------------|------------------------------------|-----------------------------|----------------------------
Example Mcnobody | ExampleMcnobody@notawebsite.com |  0.000| 0.000
                                 |                                    | NOMINAL SUM: 0.00       | ACTUAL SUM: 0.00

The "Nominal fraction of revenue" column values are to be chosen by the party adding each row.

The "NOMINAL SUM" value is the sum of the "Nominal fraction of revenue" column and must be recalculated each time a row is added or modified, BEFORE the "Actual fraction of revenue" column is recalculated.

The values in the "Actual fraction of revenue" column are to be calculated by the formula (x / (1 + NOMINAL SUM)), where "x" is the value in the "Nominal fraction of revenue" column in the same row. This entire column must be recalculated each time a row is added or modified.

The "ACTUAL SUM" value is the sum of the "Actual fraction of revenue" column and must be recalculated each time a row is added or modified, AFTER the "Actual fraction of revenue" column is recalculated.


# NO WARRANTY

## 15.

THERE IS NO WARRANTY FOR THE LIBRARY, TO THE EXTENT PERMITTED BY APPLICABLE LAW. EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT HOLDERS AND/OR OTHER PARTIES PROVIDE THE LIBRARY "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE LIBRARY IS WITH YOU. SHOULD THE LIBRARY PROVE DEFECTIVE, YOU ASSUME THE COST OF ALL NECESSARY SERVICING, REPAIR OR CORRECTION.

## 16.

IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MAY MODIFY AND/OR REDISTRIBUTE THE LIBRARY AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE THE LIBRARY (INCLUDING BUT NOT LIMITED TO LOSS OF DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD PARTIES OR A FAILURE OF THE LIBRARY TO OPERATE WITH ANY OTHER SOFTWARE), EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.


# END OF TERMS AND CONDITIONS
