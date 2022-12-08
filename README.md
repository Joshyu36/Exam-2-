# Exam-2-
## Part A
### Rules
All tokens/lexemes must be seperated by a single space

Any and all code must start with an `open` and a end with a `close`

Code is then written in `<story>` between a `open` and a `close`
### Statements
#### Declaration Statements
Begins with a type keyward, followed by the name of what is being declared, then ending with a `;`.
#### Assignment Statements
Begins with a variable that already exists. If the variable does not exist than an error occurs. The variable is then followed by a `=` then an expression that will be assigned to the variable. The statement ends with a `;`.
#### Condition Statements
Includes if statements `<ifst>` and switch statements `<optionst>`.

If statements begin with the keyword `hmm` followed by `( <coin> )` then a `{ dialogue }`. You can also add on the keyword `huh` after the initial `hmm` followed by `{ dialogue }`.

Switch statements begin with the keyword `options` followed by a `( <purpose> ) {`. Each case begins with the keyword `option` followed by a `<purpose>` then a `dialogue`, ending with a `;` and a `}` after all cases were created
#### Loop Statements
Includes for loops `<flp>` and while loops `<whlp>`

For loops begin with the keyword `since` then followed by `( <ast> ";" <coin> ";" <purpose> )` and then a `dialogue`. This will run until the `<coin>` is false.

While loops begin with the keyword `as`, followed by `( <coin> )`, then a `dialogue`. This will run until the `<coin>` is false.
#### Math Expressions

## Part B
```
<Book> --> open <dialogue> close
<dialogue> --> <ifst> | <whlp> | <ast> | <optionst> | <flp> | <story>
<story> --> "{" { <dialogue> ";" } "}"
<ifst> --> "hmm" "(" <coin> ")" <dialogue> [ "huh" <dialogue> ]
<flp> --> "since" "( <ast> ";" <coin> ";" <purpose> )" <dialogue>
<whlp> --> "as" "(" <coin> ")" <dialogue>
<ast> --> "me" "=" <purpose>
<option> --> <option> <me> ":" <dialogue> ";"
<optionst> --> "options" "("<purpose>")" "{" <option>
<name> --> <group> <me> ";" | <group> <ast> ";"
<me> --> <let> | "_" <let>
<let> --> [a-zA-Z_]{6,8}
<group> --> <solo> | <party> | <numb> | <lnumb>
<purpose> --> <goal> { ( "+" | "-" ) <goal> }
<goal> --> <task> { ( "*" | "/" | "%" ) } <task> }
<task> --> "me" | "num" | "flyl" | "(" <purpose> ")"
<num> --> [0-9] | <num>
<coin> --> <me> ( "<" | "<=" | ">" | ">=" ) <purpose> 
<deny> --> "!" <task>
<numoneb> --> <num> "_" "1"
<numtwob> --> <num> "_" "2"
<numforb> --> <num> "_" "4"
<numateb> --> <num> "_" "8"
Precedence
E --> E++ | ++E
E --> E * T
E --> E + T
E --> T
T --> T-- | --T
T --> T / F
T --> T - F
T --> T % F
F --> (E)
```
