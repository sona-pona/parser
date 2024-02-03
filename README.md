# SonaPona Parser

## Glossary

1. **Dataset**: A collection of related "Samples" grouped by theme, language, difficulty level, or other categorizations. Each "Dataset" focuses on a specific area of knowledge or skill.

2. **Sample**: An individual exercise or task within a "Dataset" that the user interacts with. "Samples" are the primary unit of practice and may contain text, audio, images, or video for typing challenges.



## EBNF

```ebnf
template separator = beginl, "===", { hwhite }, endl ;
wan separator = beginl, "---", { hwhite }, endl ;
wan mute = [ template, template separator ], card, { card separator, card } ;
template = wan ;

wan = { white | identifier | lisp | word | punctation | input } ;
thin separator = { white }, "|", { white } ;
separator = { white } | thin separator ;
function call = "{", function name, { separator, arg }, "}" ;
arg = function call | str ;

str = word | "\"", {char}, "\"" | "'", {char}, "'" ;
identifier = "$", identifier name ;
word = letter, { letter } ;
identifier name = letter, { letter | digit } ;
comment = "#", { all characters - "\n" } ;
endl = [ comment ], "\n" ;
beginl = ? start of line ? ;
white = hwhite | "\n" ;
hwhite = " " | "\t" ;
all characters = ? all visible characters ? ;
```


