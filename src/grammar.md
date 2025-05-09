# Grammar

```
program         = statement* EOF

statement       = assignment
                | call
                | `;`

call            = FNNAME args

args            = expr+

assignment      = NEWNAME `=` expr

expr            = booleanExpr
                | numericExpr
                | stringExpr

booleanExpr     = BOOLEAN
                | booleanUnary
                | booleanBinary
                | '(' booleanExpr ')'

booleanUnary    = `!` BOOLEAN
                | `!` booleanUnary
                | `!` '(' booleanExpr ')'

booleanBinary   = numericExpr ( `<` | `<=` | `>` | `>=` ) numericExpr
                | stringExpr ( `<` | `<=` | `>` | `>=` ) stringExpr
                | expr ( `==` | `!=` ) expr

numericExpr     = NUMBER
                | numericUnary
                | numericBinary
                | '(' numericExpr ')'

numericUnary    = `-` NUMBER
                | `-` numericUnary
                | `-` `(` numericExpr `)`

numericBinary   = numericExpr ( `+` | `-` | `*` | `/` ) numericExpr

stringExpr      = STRING
                | stringBinary
                | '(' stringExpr ')'

stringBinary    = stringExpr `++` stringExpr


BOOLEAN         = `true`
                | `false`
                | <name with boolean type>

NUMBER          = [0-9]+ ( `.` [0-9]+ )?
                | <name with number type>

STRING          = `"` <any printable character>* `"`
                | <name with string type>
```
