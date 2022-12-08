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
#### Tokens
##### Math Operators
| Token | Symbol | Regex |
| --- | --- | --- |
| ADDING | + | + |
| SUBTRACTING | - | - |
| MULTIPLYING | * | * |
| DIVIDING | / | / |
| OPENP | ( | ( |
| CLOSEP | ) | ) |
##### Comparison Operators
| Token | Symbol | Regex |
| --- | --- | --- |
| LT | < | < |
| GT | > | > |
| LTE | <= | <= |
| GTE | >= | >= |
| DMATCH | == | == |
| NMATCH | != | != |
##### Integer Space Size
| Token | Condition | Regex | Size
| --- | --- | --- | --- |
| NUMONEB | -128 <= num <= 127 | \d{1,3} | 1 Byte |
| NUMTWOB | -32768 <= num <= 32767 | \d{1,5} | 2 Bytes |
| NUMFORB | 	-2147483648 <= num <= 2147483647 | \d{1,10} | 4 Bytes |
| NUMATEB | -9223372036854775808 <= num <= 9223372036854775808 | \d{1,19} | 8 Bytes |
##### Keywords
| Token | Regex |
| --- | --- |
| ME | [a-zA-Z]{6,8} |
| HMM | hmm |
| HUH | huh |
| SINCE | since |
| AS | as |
| OPTIONS | options |
| OPTION | option |
| OPEN | open |
| CLOSE | close |
##### Other Symbols
| Token | Symbol | Regex |
| --- | --- | --- |
| BECOMES | = | = |
| BEGIN | { | { |
| END | } | } |
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
## Part C
Is an LL(1) grammar when reading rule set from left to right
## Part D
Rule set is nonambiguous
