---
annotation-target: Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf
date created: Wednesday, January 25th 2023, 12:13:30 pm
date modified: Wednesday, January 25th 2023, 12:15:06 pm
---


>%%
>```annotation-json
>{"created":"2023-01-25T11:18:17.504Z","text":"A lexer or scanner or lexical analyzer is something that takes a source text and then split it into blocks that are atomic, called lexemes, tokens, or atoms.\n","updated":"2023-01-25T11:18:17.504Z","document":{"title":"158540_3_En_Print.indd","link":[{"href":"urn:x-pdf:a9b812f53f00400212a3492733b3e850"},{"href":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf"}],"documentFingerprint":"a9b812f53f00400212a3492733b3e850"},"uri":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf","target":[{"source":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf","selector":[{"type":"TextPositionSelector","start":908726,"end":908913},{"type":"TextQuoteSelector","exact":"The task of a lexical analyzer (or scanner) is to segment the source text into thelexical elements, called lexemes or tokens, such as identifiers, integer or real con-stants and comments.","prefix":"alysis with Attribute Evaluation","suffix":" Lexemes are the smallest substr"}]}]}
>```
>%%
>*%%PREFIX%%alysis with Attribute Evaluation%%HIGHLIGHT%% ==The task of a lexical analyzer (or scanner) is to segment the source text into thelexical elements, called lexemes or tokens, such as identifiers, integer or real con-stants and comments.== %%POSTFIX%%Lexemes are the smallest substr*
>%%LINK%%[[#^7le48360zt5|show annotation]]
>%%COMMENT%%
>A lexer or scanner or lexical analyzer is something that takes a source text and then split it into blocks that are atomic, called lexemes, tokens, or atoms.
>
>%%TAGS%%
>
^7le48360zt5


>%%
>```annotation-json
>{"created":"2023-01-25T11:19:31.783Z","text":"A lexem, atom or token is something that has some meaning on its own and is the smallest substring possible without losing the first property (meaning).\nHence why in : \"I begin to fear that this task is very hard to do\". The correct lexems would be :\n\"I\", \" \", \"begin\", \" \", \"to\", \" \", \"fear\", \" \", \"that\", \" \", \"this\", \" \", \"task\", \" \", \"is\", \" \", \"very\", \" \", \"hard\", \" \", \"to\", \" \", \"do\", \" \"\nAn incorrect lexem would be \"ear\", it has meaning but it removes the original meaning of the lexem.","updated":"2023-01-25T11:19:31.783Z","document":{"title":"158540_3_En_Print.indd","link":[{"href":"urn:x-pdf:a9b812f53f00400212a3492733b3e850"},{"href":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf"}],"documentFingerprint":"a9b812f53f00400212a3492733b3e850"},"uri":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf","target":[{"source":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf","selector":[{"type":"TextPositionSelector","start":908914,"end":909139},{"type":"TextQuoteSelector","exact":"Lexemes are the smallest substrings that can be invested withsome semantic property. For instance, in many languages the keyword begin hasthe property of opening a compound statement, whereas its substring egin has nomeaning.","prefix":"r real con-stants and comments. ","suffix":"Each technical language uses a f"}]}]}
>```
>%%
>*%%PREFIX%%r real con-stants and comments.%%HIGHLIGHT%% ==Lexemes are the smallest substrings that can be invested withsome semantic property. For instance, in many languages the keyword begin hasthe property of opening a compound statement, whereas its substring egin has nomeaning.== %%POSTFIX%%Each technical language uses a f*
>%%LINK%%[[#^20edp3406sh|show annotation]]
>%%COMMENT%%
>A lexem, atom or token is something that has some meaning on its own and is the smallest substring possible without losing the first property (meaning).
>Hence why in : "I begin to fear that this task is very hard to do". The correct lexems would be :
>"I", " ", "begin", " ", "to", " ", "fear", " ", "that", " ", "this", " ", "task", " ", "is", " ", "very", " ", "hard", " ", "to", " ", "do", " "
>An incorrect lexem would be "ear", it has meaning but it removes the original meaning of the lexem.
>%%TAGS%%
>
^20edp3406sh


>%%
>```annotation-json
>{"created":"2023-01-25T11:24:54.919Z","text":"A technical language is just something that defines a possible lexem.\nIt is important to note that contrary to the next phase. The phase of producing lexem should not be ambiguous.","updated":"2023-01-25T11:24:54.919Z","document":{"title":"158540_3_En_Print.indd","link":[{"href":"urn:x-pdf:a9b812f53f00400212a3492733b3e850"},{"href":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf"}],"documentFingerprint":"a9b812f53f00400212a3492733b3e850"},"uri":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf","target":[{"source":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf","selector":[{"type":"TextPositionSelector","start":909139,"end":909384},{"type":"TextQuoteSelector","exact":"Each technical language uses a finite collection of lexical classes, as the ones justmentioned. A lexical class is a regular formal language: a typical example is the classof identifiers, defined by the regular expression of Example2.27 on p.29.","prefix":"ts substring egin has nomeaning.","suffix":" A lexeme of an identifier class"}]}]}
>```
>%%
>*%%PREFIX%%ts substring egin has nomeaning.%%HIGHLIGHT%% ==Each technical language uses a finite collection of lexical classes, as the ones justmentioned. A lexical class is a regular formal language: a typical example is the classof identifiers, defined by the regular expression of Example2.27 on p.29.== %%POSTFIX%%A lexeme of an identifier class*
>%%LINK%%[[#^xcpf2kour2f|show annotation]]
>%%COMMENT%%
>A technical language is just something that defines a possible lexem.
>It is important to note that contrary to the next phase. The phase of producing lexem should not be ambiguous.
>%%TAGS%%
>
^xcpf2kour2f


>%%
>```annotation-json
>{"created":"2023-01-25T11:32:13.898Z","text":"The syntactic level require for it to be fed lexemes.","updated":"2023-01-25T11:32:13.898Z","document":{"title":"158540_3_En_Print.indd","link":[{"href":"urn:x-pdf:a9b812f53f00400212a3492733b3e850"},{"href":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf"}],"documentFingerprint":"a9b812f53f00400212a3492733b3e850"},"uri":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf","target":[{"source":"vault:/Books/(Texts in Computer Science) Stefano Crespi Reghizzi, Luca Breveglieri, Angelo Morzenti - Formal Languages and Compilation (3rd Edition)-Springer (2019).pdf","selector":[{"type":"TextPositionSelector","start":909479,"end":909788},{"type":"TextQuoteSelector","exact":"In language reference manuals, we find two levels of syntactic specifications: fromlower to higher, the lexical and syntactic levels. The former defines the form of thelexemes. The latter assumes the lexemes are given in the text, and considers themto be the characters of the terminal alphabet of its syntax.","prefix":" corresponding regular language.","suffix":" Moreover, some lexemesmay carry"}]}]}
>```
>%%
>*%%PREFIX%%corresponding regular language.%%HIGHLIGHT%% ==In language reference manuals, we find two levels of syntactic specifications: fromlower to higher, the lexical and syntactic levels. The former defines the form of thelexemes. The latter assumes the lexemes are given in the text, and considers themto be the characters of the terminal alphabet of its syntax.== %%POSTFIX%%Moreover, some lexemesmay carry*
>%%LINK%%[[#^q51483a70d|show annotation]]
>%%COMMENT%%
>The syntactic level require for it to be fed lexemes.
>%%TAGS%%
>
^q51483a70d
