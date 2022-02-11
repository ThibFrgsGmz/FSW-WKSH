| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |


Cobra is a fast code analyzer that can probe and query up to millions of lines of code interactively.

Although a large number of query and rule libraries targeting C or similar languages have been developed and are included in the distribution, the basic design of the tool is language neutral.

The first version of the tool (version 1.0) was created at NASA/JPL and was made available to the public in April 2016.

Versions 2 and 3 of the tool are extended versions that can handle interactive analysis of code bases with up to millions of lines of code, while supporting a significantly richer inline query scripting language.

They also include multi-core support for a variety of queries, as well as a new set of cybersecurity-related checks.

The current version (3.0) is a significantly expanded version of the tool that was released in June 2019 under the same license.

Cobra can analyze C, C++, Ada and Python, and can relatively easily be converted back to other languages. The distribution includes sample query and script libraries.

A complete online tutorial and demonstration of Cobra version 3.1 is available at this link: http://spinroot.com/cobra/newtutorial/index.html.

If you just want to watch the demo, see this link: http://spinroot.com/cobra/newtutorial/MP4/Demo.mp4

Keynote presentation slides at SMC-IT, July 31, 2019, Pasadena, CA: http://spinroot.com/cobra/pdf/SMCIT_July_31_2019.pdf

---

Q: You mentioned that about 50% of MISRAs can be verified. Can you give an example of a MISRA rule that is difficult or impractical to verify in COBRA?

A: Some rules are not really in the scope of static analysis. There is a file in the rules/misra directory that lists these rules, and separately from the rules we are still working on.
An example of a rule from misra1997 that we are not yet checking is "Rule 29 (mandatory) The use of a tag must agree with its declaration."  -- Implementing this check needs a little more work!

---

Q: Are there any query libraries available for use? (e.g., the cobra script from P10)
What are the issues with running cobra analysis on existing code (or running cobra iteratively, and deciding not to change anything)?  Can we exclude code from the query?

A: Yes, the libraries are part of the distribution (they are all in the rules/ directory, including the P10 checkers).
You can exclude code from a request, for example by filtering on filenames (or simply by not including these files on the command line when starting cobra).
But cobra obviously doesn't care if you fix something or not.
The warnings/matches are produced on stdout, or in JSON files, and one can post-process these files to remove uninteresting results.

---

Q: How skilled do you have to be to write good models to avoid false positives?

A: That's one of the advantages of interactive query resolution: you see immediately if the match is not what you wanted and you can then iterate until you get exactly what you were hoping for.

---

Q: Does Cobra do macro expansion? Manually running the preprocessor before entering Cobra may not produce the desired results.

A: You will be happy to know that Cobra can do macro expansion.


---

Note from Amalaye Oyake (Blue Origin): I use Cobra. It is a great tool. Everyone should use it for code reviews.

Link to the open source tool: https://github.com/nimble-code/Cobra


