# Listas

Listas são coleções de dados que podem incluir diversos tipos, além de valores não exclusivos. No elixir, elas são implementadas como listas encadeadas. Isso significa que cada elemento da lista é uma referência para um outro elemento da lista. Dessa forma, ela será executada em tempo linear (`0(n)`). Assim, é mais rápido inserir um elemento no inicio da lista (prepending) e remover um elemento do final da lista (appending).

```elixir
iex> lista = [1, :dois, "Três"]
[1, :dois, "Três"]
#exemplo de prepending
iex>[0 | lista]
[0, 1, :dois, "Três"]
#exemplo de appending
iex> lista ++ [:quatro]
[1, :dois, "Três", :quatro]
```

## Concatenando listas

Para concatenar listas, utilizamos o operador `++/2` (o "/2" representa a aridade da função, falaremos sobre isso mais adiante). Ele recebe duas listas e retorna uma nova lista com todos os elementos das duas listas.

```elixir
iex> [1, 2] ++ [3, 4]
[1, 2, 3, 4]
```

## Subtraindo Listas

Para subtrair listas, utilizamos o operador `--/2`.

```elixir
iex> [1, 2, 3] -- [2, 3]
[1]
```

Duas coisas são importantes de serem observadas:

1. Sempre que a lista possui valores duplicados, o operador `--/2`irá remover somente a primeira ocorrência.

```elixir
iex> [1, 2, 3, 4, 2] -- [2, 3]
[1, 4. 2]
```

2. O operador `--/2` utiliza comparação estrita, ou seja, não é possível comparar elementos de listas com tipos diferentes.

```elixir
iex> [1, 2, 3] -- [2, "3"]
[1, 3]
iex> [1.0, 2.0] - [1.0, 2.0]
[]
```

## Trabalhando com o topo e a cauda da listas

O topo é o primeiro elemento da lista, e a cauda é o restante da lista. No elixir, temos duas funções para acessar o topo e a cauda da lista: `hd/1` e `tl/1`. Elas recebem uma lista e retornam o primeiro elemento e o restante da lista, respectivamente.
Além destas duas funções, podemos utilizar pattern matching para acessar o topo e a cauda da lista, utilizando o operador `|` para dividir a função em duas partes.

```elixir
iex> hd [1, 2, 3]
1
iex> tl [1, 2, 3]
[2, 3]
#utilizando pattern matching
iex> [head | tail] = [1, 2, 3]
[1, 2, 3]
iex> head
1
iex> tail
[2, 3]
```