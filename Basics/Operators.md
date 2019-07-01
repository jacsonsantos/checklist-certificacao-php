# Operadores
Um operador é algo que recebe um ou mais valores e que devolve outro valor após executar uma ou mais expressões.

### Precedência de Operadores
A precedência de um operador especifica quem tem mais prioridade quando há duas delas juntas. Por exemplo, na expressão `1 + 5 * 3`, a resposta é 16 e não 18 porque o operador de multiplicação (`*`) tem prioridade de precedência que o operador de adição (`+`). Parênteses podem ser utilizados para forçar a precedência, se necessário. Assim, `(1 + 5) * 3` é avaliado como 18. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.precedence.php)

```php
<?php
$a = 3 * 3 % 5; // (3 * 3) % 5 = 4

$a = 1;
$b = 2;
$a = $b += 3; // $a = ($b += 3) -> $a = 5, $b = 5
?>
```

### Operadores Aritméticos
Lembra-se da aritmética básica da escola? Estes operadores funcionam exatamente como aqueles. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.arithmetic.php)

| nome | operador | exemplo |
|------|----------|---------|
| Identidade | `+` | `+$a` |
| Negação | `-` | `-$a` |
| Adição | `+` | `$a + $b` |
| Subtração | `-` | `$a - $b` |
| Multiplicação | `*` | `$a * $b` |
| Divisão | `/` | `$a / $b` |
| Módulo | `%` | `$a % $b` |
| Exponencial | `**` | `$a**$b` |

```php
<?php
$a = 2;
$b = 5;

var_dump(+$a); // int(2)
var_dump(-$b); // int(-5)
var_dump($a + $b); // int(7)
var_dump($b - $a); // int(3)
var_dump($a * $b); // int(10)
var_dump($b / $a); // float(2.5)
var_dump($b % $a); // int(1)
var_dump($b ** $a); // int(25)
```

### Operadores de Atribuição
O operador básico de atribuição é `=`. A sua primeira inclinação deve ser a de pensar nisto como **"é igual"**. Não! Isto quer dizer, na verdade, que o operando da esquerda recebe o valor da expressão da direita (ou seja, **"é definido para"**). [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.assignment.php)

```php
<?php
$a = 5; // $a recebe 5
$b = $a + 4; // $b é igual a 9 agora e $a foi definido como 5

```

### Operadores bit a bit (bitwise)
Operadores bit-a-bit permitem a avaliação e modificação de bits específicos em um tipo inteiro. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.bitwise.php)

| nome | operador | exemplo |
|------|----------|---------|
| E (AND) | `&` | `$a & $b` |
| OU (OR inclusivo) | ` | ` | ` $a | $b ` |
| XOR (OR exclusivo) | `^` | `$a ^ $b` |
| NÃO (NOT) | `~` | `~ $a` |
| Deslocamento à esquerda | `<<` | `$a << $b` |
| Deslocamento à direita | `>>` | `$a >> $b` |

```php
<?php
$a = 2;
$b = 5;

var_dump($a & $b); // int(0)
var_dump($a | $b); // int(7)
var_dump($a ^ $b); // int(7)
var_dump(~ $a); // int(-3)
var_dump($a << $b); // int(64)
var_dump($a >> $b); // int(0)
```

### Operadores de Comparação
Operadores de comparação, como os seus nomes implicam, permitem que você compare dois valores. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.comparison.php)

| nome | operador | exemplo |
|------|----------|---------|
| Igual | `==` | `$a == $b` |
| Idêntico | `===` | `$a === $b` |
| Diferente | `!=` | `$a != $b` |
| Diferente | `<>` | `$a <> $b` |
| Não idêntico | `!==` | `$a !== $b` |
| Menor que | `<` | `$a < $b` |
| Maior que | `>` | `$a > $b` |
| Menor ou igual | `<=` | `$a <= $b` |
| Maior ou igual | `>=` | `$a >= $b` |
| Spaceship (nave espacial) | `<=>` | `$a <=> $b` |

```php
<?php
$a = 2;
$b = '2';
$c = 5;
$d = 1;

var_dump($a == $b); // bool(true)
var_dump($a === $b); // bool(false)
var_dump($a != $b); // bool(false)
var_dump($a <> $b); // bool(false)
var_dump($a !== $b); // bool(true)
var_dump($a < $c); // bool(true)
var_dump($a > $c); // bool(false)
var_dump($a <= $c); // bool(true)
var_dump($a >= $c); // bool(false)

var_dump($a <=> $c); // int(-1)
var_dump($a <=> $b); // int(0)
var_dump($a <=> $d); // int(1)
```

**Dica:** [Tabela de comparações de tipos do PHP](https://www.php.net/manual/pt_BR/types.comparisons.php)

### Operadores de controle de erro
O PHP suporta um operador de controle de erro: o sinal 'arroba' (`@`). Quando ele precede uma expressão em PHP, qualquer mensagem de erro que possa ser gerada por aquela expressão será ignorada. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.errorcontrol.php)

```php

<?php
/* Erro de arquivo intencional */
$my_file = @file('arquivo_nao_existente') or die ("Falha abrindo arquivo: '$php_errormsg'");

// Isto funciona para qualquer expressão, não apenas para funções:
$value = @$cache[$key];
// você não receberá nenhum aviso se a chave $key não existir.
```

### Operadores de Execução
O PHP suporta um operador de execução: acentos graves (` `` `). Note que não são aspas simples! O PHP tentará executar o conteúdo dentro dos acentos graves como um comando do shell; a saída será retornada (isto é, ela não será simplesmente mostrada na tela; ela pode ser atribuída a uma variável). A utilização do operador acento grave é idêntica a da função [shell_exec()](https://www.php.net/manual/pt_BR/function.shell-exec.php). [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.execution.php)

```php

<?php
$output = `ls -al`;
echo "<pre>$output</pre>";
```
**Nota:** O operador de execução fica desabilitado quando `safe mode` está ativo ou `shell_exec()` está desabilitado.

### Operadores de Incremento/Decremento
O PHP suporta operadores de pré e pós-incremento e decremento no estilo C. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.increment.php)

| nome | operador| exemplo |
|------|---------|---------|
| Pré-incremento | `++` | `++$a` |
| Pós-incremento | `++` | `$a++` |
| Pré-decremento | `--` | `--$a` |
| Pós-decremento | `--` | `$a--` |

**Nota:** Os operadores incremento/decremento afetam apenas números e *strings*. *Arrays*, objetos e recursos não são afetados. Decrementar `NULL` não gera efeitos, mas incrementar resulta em `1`.

```php
<?php
$a = 1;
$b = 2;
$c = NULL;

var_dump($a++); // int(1)
var_dump($a + $b); // int(4)
var_dump(++$a); // int(3)

var_dump($b--); // int(2)
var_dump($b + $a); // int(4)
var_dump(--$b); // int(0)

var_dump($c++); // NULL
var_dump($c); // int(1)
```

### Operadores Lógicos
As operações lógicas trabalham sobre valores *booleanos*, um dado booleano só pode assumir dois valores **VERDADEIRO** ou **FALSO**. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.logical.php)

| nome | operador| exemplo |
|------|---------|---------|
| E | `and` | `$a and $b` |
| OU | `or` | `$a or $b` |
| XOR | `xor` | `$a xor $b` |
| NÃO | `!` | `! $a` |
| E | `&&` | `$a && $b` |
| OU | `||` | `$a || $b` |

```php
<?php
$a = true;
$b = false;

var_dump($a and $b); // bool(false)
var_dump($a or $b); // bool(true)
var_dump($a xor $b); // bool(true)
var_dump(!$a); // bool(false)
var_dump($a && $b); // bool(false)
var_dump($a || $b); // bool(true)
```

### Operadores de String
Há dois operadores de string. O primeiro é o operador de **concatenação** (`.`), que retorna a concatenação dos seus argumentos direito e esquerdo. O segundo é o operador de **atribuição de concatenação** (`.=`), que acrescenta o argumento do lado direito no argumento do lado esquerdo. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.string.php)

| nome | operador| exemplo |
|------|---------|---------|
| concatenação | `.` | `$a = $a . $b` |
| atribuição de concatenação | `.=` | `$a .= $b` |

```php
<?php
$a = "Olá ";
$b = $a . "mundo!"; // agora $b contém "Olá mundo!"

$a = "Olá ";
$a .= "mundo!";     // agora $a contém "Olá mundo!"
```

### Operadores de Arrays
O operador `+` retorna o *array* à direta anexado ao *array* da esquerda. Para chaves que existam nos dois *arrays* os elementos do *array* à esquerda serão mantidos, os valores de mesma chave no *array* da direita são ignorados. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.array.php)

| nome | operador| exemplo |
|------|---------|---------|
| União | `+` | `$a + $b` |
| Igualdade | `==` | `$a == $b` |
| Identidade | `===` | `$a === $b` |
| Desigualdade | `!=` | `$a != $b` |
| Desigualdade | `<>` | `$a <> $b` |
| Não identidade | `!==` | `$a !== $b` |

```php
<?php
$a = array("a" => "maçã", "b" => "banana");
$b = array("a" =>"pêra", "b" => "framboesa", "c" => "morango");

var_dump($a + $b);
/*
array(3) { 
["a"]=> string(6) "maçã" 
["b"]=> string(6) "banana" 
["c"]=> string(7) "morango" 
}
*/

var_dump($a == $b); // bool(false)
var_dump($a === $b); // bool(false)
var_dump($a != $b); // bool(true)
var_dump($a <> $b); // bool(true)
var_dump($a !== $b); // bool(true)
```

### Operadores de tipo
`instanceof` é usado para determinar se um variável do PHP é um objeto instânciado de uma certa classe. [Saiba mais](https://www.php.net/manual/pt_BR/language.operators.type.php)

```php
<?php
class MyClass{}
class NotMyClass {}

$a = new MyClass;

var_dump($a instanceof MyClass); // bool(true)
var_dump($a instanceof NotMyClass); // bool(false)
```
