# Grammar

## Syntax Grammar

```
program         = statement* EOF

statement       = assignment
                | call
                | ifStmt
                | block
                | `;`

block           = `{` statement* `}`

ifStmt          = `if` booleanExpr statement ( `else` statement )?

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
```

## Lexical Grammar

```
BOOLEAN         = `true`
                | `false`
                | <name with boolean type>

NUMBER          = [0-9]+ ( `.` [0-9]+ )?
                | <name with number type>

STRING          = `"` <any printable character>* `"`
                | <name with string type>

FNNAME          = <uppercase letter> [a-z0-9_]*
```
