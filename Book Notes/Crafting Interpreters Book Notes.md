---
annotation-target: Books/Crafting Interpreters.pdf
date created: Tuesday, February 7th 2023, 9:37:15 am
date modified: Tuesday, February 7th 2023, 9:37:50 am
---


>%%
>```annotation-json
>{"created":"2023-02-07T08:38:44.391Z","text":"So there is a grammar for the lexical analysis and a grammar for the synthax analysis\n","updated":"2023-02-07T08:38:44.391Z","document":{"title":"Crafting Interpreters.pdf","link":[{"href":"urn:x-pdf:62c154ebe07241608ca8b08306dd2668"},{"href":"vault:/Books/Crafting Interpreters.pdf"}],"documentFingerprint":"62c154ebe07241608ca8b08306dd2668"},"uri":"vault:/Books/Crafting Interpreters.pdf","target":[{"source":"vault:/Books/Crafting Interpreters.pdf","selector":[{"type":"TextPositionSelector","start":154419,"end":154518},{"type":"TextQuoteSelector","exact":" lexical grammar—the rules for how characters get grouped into tokens—was called a regular language","prefix":"rmalism we used for defining the","suffix":". That was fine for our scanner,"}]}]}
>```
>%%
>*%%PREFIX%%rmalism we used for defining the%%HIGHLIGHT%% ==lexical grammar—the rules for how characters get grouped into tokens—was called a regular language== %%POSTFIX%%. That was fine for our scanner,*
>%%LINK%%[[#^u3jqxfm3bd|show annotation]]
>%%COMMENT%%
>So there is a grammar for the lexical analysis and a grammar for the synthax analysis
>
>%%TAGS%%
>
^u3jqxfm3bd


>%%
>```annotation-json
>{"created":"2023-02-07T08:43:54.904Z","text":"A grammar has an alphabet.\nAn alphabet is a set of atomic elements.\nIf multiple element of an alphabet are grouped together in a manner that correspond to the rules set by the grammar we have a sentence. ","updated":"2023-02-07T08:43:54.904Z","document":{"title":"Crafting Interpreters.pdf","link":[{"href":"urn:x-pdf:62c154ebe07241608ca8b08306dd2668"},{"href":"vault:/Books/Crafting Interpreters.pdf"}],"documentFingerprint":"62c154ebe07241608ca8b08306dd2668"},"uri":"vault:/Books/Crafting Interpreters.pdf","target":[{"source":"vault:/Books/Crafting Interpreters.pdf","selector":[{"type":"TextPositionSelector","start":154692,"end":155037},{"type":"TextQuoteSelector","exact":"We need a bigger hammer, and that hammer is a context-free grammar (CFG). It’s the next heaviest tool in the toolbox of formal grammars. A formal grammar takes a set of atomic pieces it calls its “alphabet”. Then it defines a (usually infinite) set of “strings” that are “in” the grammar. Each string is a se-quence of “letters” in the alphabet.","prefix":"ch can nest arbi-trarily deeply.","suffix":"I’m using all those quotes becau"}]}]}
>```
>%%
>*%%PREFIX%%ch can nest arbi-trarily deeply.%%HIGHLIGHT%% ==We need a bigger hammer, and that hammer is a context-free grammar (CFG). It’s the next heaviest tool in the toolbox of formal grammars. A formal grammar takes a set of atomic pieces it calls its “alphabet”. Then it defines a (usually infinite) set of “strings” that are “in” the grammar. Each string is a se-quence of “letters” in the alphabet.== %%POSTFIX%%I’m using all those quotes becau*
>%%LINK%%[[#^jaid1m57ca|show annotation]]
>%%COMMENT%%
>A grammar has an alphabet.
>An alphabet is a set of atomic elements.
>If multiple element of an alphabet are grouped together in a manner that correspond to the rules set by the grammar we have a sentence. 
>%%TAGS%%
>
^jaid1m57ca


>%%
>```annotation-json
>{"created":"2023-03-20T20:16:10.159Z","text":"A terminal is basically a litteral","updated":"2023-03-20T20:16:10.159Z","document":{"title":"Crafting Interpreters.pdf","link":[{"href":"urn:x-pdf:62c154ebe07241608ca8b08306dd2668"},{"href":"vault:/Books/Crafting Interpreters.pdf"}],"documentFingerprint":"62c154ebe07241608ca8b08306dd2668"},"uri":"vault:/Books/Crafting Interpreters.pdf","target":[{"source":"vault:/Books/Crafting Interpreters.pdf","selector":[{"type":"TextPositionSelector","start":157195,"end":157571},{"type":"TextQuoteSelector","exact":"A terminal is a letter from the grammar’s alphabet. You can think of it like a literal value. In the syntactic grammar we’re defining, the terminals are indi-vidual lexemes—tokens coming from the scanner like if or 1234.These are called “terminals”, in the sense of an “end point” because they don’t lead to any further “moves” in the game. You simply produce that one symbol.","prefix":"ome in two delectable flavors:• ","suffix":"• A nonterminal is a named refer"}]}]}
>```
>%%
>*%%PREFIX%%ome in two delectable flavors:•%%HIGHLIGHT%% ==A terminal is a letter from the grammar’s alphabet. You can think of it like a literal value. In the syntactic grammar we’re defining, the terminals are indi-vidual lexemes—tokens coming from the scanner like if or 1234.These are called “terminals”, in the sense of an “end point” because they don’t lead to any further “moves” in the game. You simply produce that one symbol.== %%POSTFIX%%• A nonterminal is a named refer*
>%%LINK%%[[#^3rqhkkyfwrc|show annotation]]
>%%COMMENT%%
>A terminal is basically a litteral
>%%TAGS%%
>
^3rqhkkyfwrc
