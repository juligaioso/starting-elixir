# Pattern Matching

Pattern Matching é uma forma aritmética de buscar padrões simples no elixir. Ela permite busca em valores, estruturas de dados e até mesmo em funções. 

## Operador Match

O operador `=` em elixir é chamado de match e possui uma função bem semelhante ao sinal de igualdade da matemática. Quando usado, ele transforma a expressão em uma equação e, então, passa a buscar equivalência entre os dois lados da expressão. Se a comparação for verdadeira, o valor da equação é retornado; se for falsa, ela retorna um erro

```elixir
iex> a = 1
1
```

Isso é válido para quaisquer tipos de dados.

```elixir
iex> {:ok, value} = {:ok, 1}
{:ok, 1}
iex> value
1
iex> {ok, value} = {:ok, 2}
** (MatchError) no match of right hand side value: {:error}
```

## Operador Pin

O operador `ˆ` é chamado de pin e é usado quando não queremos fazer rebind de uma variável. Assim, você pode fazer a comparação do valor da variável sem alterar seu valor

```elixir
iex> a = 1
1
iex> ˆa = 2
(MatchError) no match of right hand side value: 2
```

## Underscore

O underscore (ou underline), quando utilizado do lado esquerdo em um pattern matching é usado para ignorar um valor. É bastante utilizado quando queremos ignorar um valor em algum tipo de estrutura de dado. 

```elixir
## Os valores 2 e 3 não serão associados a nada, já que foram ignorados pelo uso do underscore
iex> {a, _, _} = {1, 2, 3}
1
```
