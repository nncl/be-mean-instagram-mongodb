#MongoDB - Aula 04 - Exercício
Autor: Cauê Bruno de Almeida

## 1. Adicionar 2 ataques ao mesmo tempo para os seguintes pokemons: Pikachu, Squirtle, Bulbassauro e Charmander.

Não tenho esses pokémons não sei o porquê. Mas vou fazer com outros que tenho.

```
var query = {name: {
    $in: [
        /pickachu/i,
        /dog pi/i,
        /Blastoise/i,
        /Mew/i
    ]}
}

var attacks = [
    'PLA',
    'POW'
]

var options = {multi: true}

var mod = {$pushAll: {moves: attacks}}

be-mean-pokemons> db.pokemons.update(query, mod, options)
Updated 5 existing record(s) in 2ms
WriteResult({
  "nMatched": 5,
  "nUpserted": 0,
  "nModified": 5
})
```

## 2. Adicionar 1 movimento em todos os pokemons: `desvio`.

```
var query = {}
var mod = {$push: {moves: 'desvio'}}
var options = {multi: true}

be-mean-pokemons> db.pokemons.update(query, mod, options)
Updated 8 existing record(s) in 2ms
WriteResult({
  "nMatched": 8,
  "nUpserted": 0,
  "nModified": 8
})
```

## 3. Adicionar o pokemon `AindaNaoExisteMon` caso ele não exista com todos os dados com o valor `null` e a descrição: 'Sem maiores informações'.

## 4. Pesquisar todos os pokemons que possuam o ataque `investida` e mais um que você adicionou, escolha o seu pokemon favorito.

## 5. Pesquisar todos os pokemons que possuam os ataques que você adicionou, escolha seu pokemon favorito.

## 6. Pesquisar todos pokemons que não são do tipo `elétrico`.

## 7. Pesquisar todos pokemons que tenham o ataque `investida` **E** tenham defesa **não menor ou igual** a 49.

## 8. Remove **todos** os pokemons do tipo água e com attack menor que 50.
