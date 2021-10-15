# Tipos básicos no Elixir

## Int

O suporte para números inteiros inclui números binários, octais e hexadecimais

```elixir
iex> 10
10
iex> 0b0010
2
iex> 0o0010
8
iex> 0x10
10
```

## Float

Pontos flutuantes possuem precisão de 64 bits e exigem pelo menos um digito inteiro e um decimal depois deste.

```elixir
iex> 0.0
0.0
iex> .1
** (SyntaxError) iex:2: syntax error before: '.'
```

## Booleanos

Os valores "true" e "false" são aceitos. Para o elixir, todo valor é "true", com excessão de "false" e "nil".

```elixir
iex> true
true
iex> false
false
```

## Strings

São representadas por aspas duplas e codificadas em UFT-8.

```elixir
iex> "Hello World"
"Hello World"
```

## atom

Átomos são constantes cujo nome é equivalente ao seu valor.

```elixir
iex> :hello
:hello
iex> :hello == :world
false
```

São também átomos os booleanos "true" e "false", além dos nomes de módulos, mesmo que o módulo ainda não tenha sido declarado.

```elixir
iex> is_atom(true)
true
iex> is_boolean(:true)
true
iex> is_atom(MyApp.MyModule)
true
```