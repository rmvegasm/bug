# What i think it's doing

When `devtools::document` encounters a left bracket `[`, it writes the correct
line:
```tex
\code{[} \code{foo[bar]}
```
followed by this line in which the character between the backticks is out of the
code construct, followed by all the characters until the next backtick within a
`\code{}` construct, and ending in a cryptic statement:
```tex
[\code{}foo[bar]: R:%60%20%60foo[bar
```
I think eventualy this leads to the "unmatched braces or quotes" error... 

-  could this error be signaled while reading the `.Rd` file?  
-  is there an intermediate form within the `roxygen` comments and the `.Rd`?
