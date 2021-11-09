# Tuplas

Tuplas são  bastante parecidas com mapas, porém ela armazena todos os dados em endereços contíguos, ou seja: ela não possui tamanho dinâmico. Isso faz com que o acesso de seu tamanho seja mais rápido, mas torna mais custosa a sua modificação (já que uma nova tupla é armazenada).
Definimos tuplas com o uso de chaves

```elixir
iex> {1, 2, 3}
{1, 2, 3}
```

## Listas de palavras chaves

As listas de palavras chaves são, assim como os mapas, estruturas de dados associativas (veremos os mapas logo a seguir). Uma lista de palavras chaves é uma lista de pares chave/valor, onde a chave é um átomo e o valor é um valor qualquer.

```elixir
iex> {a: 1, b: 2, c: 3}
{a: 1, b: 2, c: 3}
```

As listas de palavras chaves possuem três caracteristicas relevantes: 
1. As chaves são átomos, ou seja, são strings ou números.
2. As chaves não são necessariamente únicas.
3. As chaves são ordenadas.

# Mapas

Mapas são a escolha mais comum para se armazenar estruturas do tipo chave-valor. A diferença entre uma lista de palavras chaves e um mapa é que o mapa aceita chaves de qualquer tipo (e não só átomos) e que os mapas não são ordenados. A sintaxe do mapa é `%{}`.

> OBS: A partir do elixir 1.2, variáveis também são permitidas como chaves de mapas.

```elixir
iex> %{:a => 1, :b => 2, :c => 3}
{:a => 1, :b => 2, :c => 3}
iex> key = "a"
iex> %{key => 1, :b => 2, :c => 3}
{:b => 2, :c => 3, "a" => 1}
```

É importante observar que caso um elemento duplicado seja inserido no mapa, ele irá sobrescrever o valor anterior.

```elixir
iex> %{:a => 1, :b => 2, :c => 3, :a => 4}
{:a => 4, :b => 2, :c => 3}
```

Para criar uma nova chave, utilizamos a função `put/3`:

```elixir
iex> mapa = %{"a"=> 1, "b" => 2, "c" => 3}
{"a"=> 1, "b" => 2, "c" => 3}
iex> mapa.put(mapa, "d", 4)
{"a"=> 1, "b" => 2, "c" => 3, "d" => 4}
```

## Mapas que possuem somente átomos como chaves

Existe uma sintaxe especial para mapas que possuem somente átomos como chaves:

```elixir
iex> %{a: 1, b: 2, c: 3}
{a: 1, b: 2, c: 3}
iex> %{a: 1, b: 2, c: 3} == {:a => 1, :b => 2, :c => 3}
true
```

Existe também uma sintaxe especial para acessar os elementos que possuem átomos como chaves:

```elixir
iex> mapa = %{a: 1, b: 2, c: 3}
{a: 1, b: 2, c: 3}
iex> mapa.a
1
```

Uma outra sintaxe especial para mapas que possuem somente átomos como chaves é a utilizada para atualizar um elemento:

```elixir
iex> mapa = %{a: 1, b: 2, c: 3}
{a: 1, b: 2, c: 3}
iex>%{mapa | a: 4}
{a: 4, b: 2, c: 3}
```

Lembrando que essa sintaxe deve ser utilizada somente para atualizar um elemento. Caso queira modificar um elemento, deve-se utilizar a função `put/3`.
