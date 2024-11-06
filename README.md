# LFG/XLE Computational Grammar Fragment (Journal of Language Modelling, 2024)
Author: Chit Fung LAM (Lawrence)

This repository contains a computational grammar fragment developed in the Lexical-Functional Grammar (LFG) formalism. The fragment computationally implements and tests the linguistic constraints discussed in the following paper:

Lam, C.-F. (2024). Control, inner topicalisation, and focus fronting in Mandarin Chinese: modelling in parallel constraint-based grammatical architecture. Journal of Language Modelling, 12(1), 69–153. https://doi.org/10.15398/jlm.v12i1.365

The grammar fragment was written using the Xerox Linguistic Environment (XLE) developed at the Palo Alto Research Center (PARC). See [this link](https://ling.sprachwiss.uni-konstanz.de/pages/xle/) and [XLE's official document](https://ling.sprachwiss.uni-konstanz.de/pages/xle/doc/xle_toc.html) for more information about grammar engineering via XLE. XLE incorporates advanced algorithms for parsing and generating Lexical-Functional Grammars (LFGs), accompanied by a robust graphical interface for grammar creation and debugging. XLE serves as the foundation for the Parallel Grammar (ParGram) Consortium, which focuses on building grammars suitable for industrial applications. Previous and ongoing projects have developed grammars for languages such as English, French, German, Hungarian, Indonesian, Japanese, Murrinh-Patha, Norwegian, Polish, Tigrinya, Turkish, Urdu, Welsh, Wolof, Chinese (ongoing), and Irish (ongoing). XLE is coded in C, with a Tcl/Tk-based user interface, and is compatible with Solaris Unix, Linux, and Mac OS X, though Windows support is limited. The [ParGram wiki](https://wiki.uni-konstanz.de/pargram/index.php/Main_Page) provides more information about the ParGram Consortium.

## Files in the repository
1. restructuring.lfg
   
   This file is a small LFG grammar to be run by XLE. It contains the following parts:<br/>
   (i) CONFIG, which tells XLE which files and features to use with the grammar;<br/>
   (ii) morphconfig, which specifies the tokenizers;<br/>
   (iii) annotated rules;<br/>
   (iv) templates;<br/>
   (v) lexicon of a limited number of Chinese words.<br/>
   
   This grammar is capable of parsing the following linguistic structures (with a limited lexicon):<br/>
   (i) Simple SVO;<br/>
   (ii) Exhaustive control;<br/>
   (iii) Partial control;<br/>
   (iv) Non-control complementation;<br/>
   (v) Exhaustive control with inner topicalization;<br/>
   (vi) Exhaustive control with focus fronting;<br/>
   (vii) Partial control with inner topicalization;<br/>
   (viii) Partial control with focus fronting;<br/>
   (ix) Non-control complementation with inner topicalization;<br/>
   (x) Non-control complementation with focus fronting.<br/>

   NB: In large-scale grammar development, it is common to divide the grammar into separate files; as such, any .lfg file that the grammar developer wants to include must be listed in the CONFIG. Since this LFG grammar is relatively small, all of the above componenets are contained in a single file, namely restructuring.lfg.
   
3. testsuite.lfg<br/>
This file contains the sentences to be tested by parsing them through restructuring.lfg to display their linguistic analyses.

   NB: As a grammar becomes more complex and covers a larger fragment of a natural language, XLE's grammar-debugging facilities can help explore the linguistic consequences of the grammatical formulations so that gramamr developers can detect and correct both conceptual errors and errors of specification. By parsing the sentences in a testsuite using the grammar, grammar developers can then inspect the output to evaluate whether the grammar contains the correct linguistic constraints.
 
5. basic-parse-tok.fst<br/>
A simple tokenizer for parsing (this is a binary file)

6. default-gen-tokenizer.fst<br/>
A simple tokenizer for generation (this is a binary file)

   NB: XLE makes it simple to integrate finite-state tokenizers into the grammar. Tokenizers insert token boundaries between words and perform tasks such as splitting punctuation off of words and lowercase initial capitals.

## An illustration
Once a sentence is parsed, summary details—showing the count of f-structure solutions, the computation time, and the number of subtrees—are displayed below the sentence in the XLE window, with the cursor positioned at the prompt for parsing the next sentence. The linguistic representations of the sentence appear in the C-structure and F-structure windows. The following illustrates the parsing results of two examples using the gramamr.

```
% parse {xiaoming shefa mingtian wancheng zhexiang gongzuo}
parsing {xiaoming shefa mingtian wancheng zhexiang gongzuo}
1 solutions, 0.009 CPU seconds, 0.328MB max mem, 37 subtrees unified
1
```
<img width="488" alt="shefa_c-str" src="https://github.com/user-attachments/assets/5bf19465-c99d-4db4-b292-c7d8bf8729ad">
<img width="451" alt="shefa_f-str" src="https://github.com/user-attachments/assets/48b9d845-b645-4020-8095-739c6ffd9975">

```
% parse {xiaoming jueding lian zhexiang gongzuo dou mingtian wancheng}
parsing {xiaoming jueding lian zhexiang gongzuo dou mingtian wancheng}
2 solutions, 0.010 CPU seconds, 0.304MB max mem, 38 subtrees unified
2
```
<img width="514" alt="jueding_c-str" src="https://github.com/user-attachments/assets/570a9369-6e53-44ef-8c7e-925138194c4f">
<img width="495" alt="jueding_f-str" src="https://github.com/user-attachments/assets/ef6f8ac0-f576-451a-8d97-fe22f20c6fc5">


## Further information
For further information about LFG and its computational implementation, please refer to the following materials:

Forst, M. & King, T. H. (2023). Computational implementations and applications. In M. Dalrymple (Ed)., Handbook of Lexical Functional Grammar (pp. 1083-1123). Berlin: Language Science Press. DOI: 10.5281/zenodo.10185986

Butt, M., King, T. H., Niño, M.-E., & Segond, F. (1999). A Grammar Writer's Cookbook. Stanford: CSLI Publications.





