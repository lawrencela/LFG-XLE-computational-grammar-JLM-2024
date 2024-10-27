# LFG/XLE Computational Grammar Fragment (Journal of Language Modelling, 2024)
Author: Chit Fung LAM (Lawrence)

This repository contains a computational grammar fragment developed in the Lexical-Functional Grammar (LFG) formalism. The fragment computationally implements and tests the linguistic constraints discussed in the following paper:

Lam, C.-F. (2024). Control, inner topicalisation, and focus fronting in Mandarin Chinese: modelling in parallel constraint-based grammatical architecture. Journal of Language Modelling, 12(1), 69–153. https://doi.org/10.15398/jlm.v12i1.365

The grammar fragment was written using the Xerox Linguistic Environment (XLE) developed at the Palo Alto Research Center (PARC). See [this link](https://ling.sprachwiss.uni-konstanz.de/pages/xle/) and [XLE's official document](https://ling.sprachwiss.uni-konstanz.de/pages/xle/doc/xle_toc.html) for more information about grammar engineering via XLE. XLE incorporates advanced algorithms for parsing and generating Lexical-Functional Grammars (LFGs), accompanied by a robust graphical interface for grammar creation and debugging. XLE serves as the foundation for the Parallel Grammar (ParGram) Consortium, which focuses on building grammars suitable for industrial applications. Previous and ongoing projects have developed grammars for languages such as English, French, German, Hungarian, Indonesian, Japanese, Murrinh-Patha, Norwegian, Polish, Tigrinya, Turkish, Urdu, Welsh, Wolof, Chinese (ongoing), and Irish (ongoing). XLE is coded in C, with a Tcl/Tk-based user interface, and is compatible with Solaris Unix, Linux, and Mac OS X, though Windows support is limited. The [ParGram wiki](https://wiki.uni-konstanz.de/pargram/index.php/Main_Page) provides more information about the ParGram Consortium.

## Files in the repository
1. restructuring.lfg
   This file is a small LFG grammar to be run by XLE. It contains the following parts:
   (i) CONFIG, which tells XLE which files and features to use with the grammar;
   (ii) morphconfig, which specifies the tokenizers;
   (iii) annotated rules;
   (iv) templates;
   (v) lexicon of a limited number of Chinese words.
   
   This grammar is capable of parsing the following linguistic structures (with a limited lexicon):
   (i) Simple SVO;
   (ii) Exhaustive control;
   (iii) Partial control;
   (iv) Non-control complementation;
   (v) Exhaustive control with inner topicalization;
   (vi) Exhaustive control with focus fronting;
   (vii) Partial control with inner topicalization;
   (viii) Partial control with focus fronting;
   (ix) Non-control complementation with inner topicalization;
   (x) Non-control complementation with focus fronting.
   
3. testsuite.lfg
   This file contains the sentences to be tested. 
4. basic-parse-tok.fst

5. default-gen-tokenizer.fst
   

## An illustration


## Further information about LFG and computational grammar development
