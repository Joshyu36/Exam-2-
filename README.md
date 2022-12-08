# Exam-2-
#Part B
<open> --> <dialogue>
<dialogue> --> <ifst> | <whlp> | <ast> | <option> | <flp> | <story>
<story> --> "{" { <dialogue> ";" } "}"
<ifst> --> "hmm" "(" <coin> ")" <dialogue> [ "huh" <dialogue> ]
<whlp> --> "as" "(" <coin> ")" <dialogue>
<ast> --> "me" "=" <purpose>
<option> --> <option> <me> ":" <dialogue> ";"
<optionst> --> <options> "("<purpose>")" "{" <option>
<name> --> <group> <me> ";" | <group> <ast> ";"
<me> --> <let> | "_" <let>
<let> --> a | b | c | ... | z | A | B | C | ... | Z
<group> --> <solo> | <party> | <numb> | <lnumb>
<purpose> --> <goal> { ( "+" | "-" ) <goal> }
<goal> --> <task> { ( "*" | "/" | "%" ) } <task> }
<task> --> "me" | "num" | "flyl" | "(" <purpose> ")"
<num> --> 0 | 1 | 2 | ... | 9
<coin> --> <me> <compare> <purpose> 
<compare> --> < | > | == | <= | >= | !=
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
