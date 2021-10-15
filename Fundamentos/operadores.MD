# Operadores

## Aritméticos
O elixir suporta os operadores básicos "+", "-", "*" e "/". Com eles, você pode fazer operações com variáveis e constantes que sejam do mesmo tipo. O retorno geralmente é um número do mesmo tipo, exceto com o operador "/", que sempre retorna um float.

```elixir
iex> 1 + 1
2
iex> 2 - 1
1
iex> 2 * 2
4
iex> 4 / 2
2.0
iex> 3/2
1.5
```

### Casos especiais de divisão

O elixir possui duas funções úteis para casos em que você quer resultados diferentes da divisão:

```elixir
iex> div(3, 2)
1
```

O operador `div()` é usado quando você quer receber o resultado inteiro de uma divisão, ignorando a parte decimal.

```elixir
iex> rem(3, 2)
1
```

O operador `rem()` retorna o resto de uma divisão.

## Booleanos

Temos, no elixir, suporte para os operadores booleanos "||", "&&" e "!". Eles suportam qualquer tipo, e o tipo do retorno depende do resultado da operação.

```elixir
iex> 2 || true
2
iex> false || 10
10

iex> 2 && nil
nil
iex> 2 && false
false

iex> !true
false
iex> !2
false
```

## Comparação

No Elixir possui os operadores de comparação "==", "!=", "===", "!==", "<=", ">=", "<" e ">". Uma caracteristica interessante do elixir é que qualquer tipo pode ser comparado, e o retorno será um booleano que segue a ordem de classificação dos tipos:

```elixir
number < atom < reference < function < port < pid < tuple < map < list < bitstring
```

Outro ponto que devemos sempre ficar atentos é com comparações entre inteiros e pontos flutuantes. Caso o tipo também deva ser levado em consideração, devemos utilizar os operadores "==="e "!==" no lugar de "=="e "!=".

```elixir
iex> 2 == 2.0
true

iex> 2 === 2.0
false
```
