# SonaPona Parser

## EBNF

```ebnf
template separator = beginl, "===", { hspace }, endl ;
wan separator = beginl, "---", { hspace }, endl ;
wan mute = [ template, template separator ], card, { card separator, card } ;
template = wan ;

wan = { white | identifier | lisp | word | punctation | input } ;
thin separator = { space }, "|", { space } ;
separator = { space } | thin separator ;
function call = "{", function name, { separator, arg }, "}" ;
arg = function call | str ;

str = word | "\"", {char}, "\"" | "'", {char}, "'" ;
identifier = "$", identifier name ;
word = letter, { letter } ;
identifier name = letter, { letter | digit } ;
comment = "#", { all characters - "\n" } ;
endl = [ comment ], "\n" ;
beginl = ? start of line ? ;
space = hspace | "\n" ;
hspace = " " | "\t" ;
all characters = ? all visible characters ? ;
```
