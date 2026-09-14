# Pokédex — consumindo a PokéAPI

Página HTML/JavaScript que busca um Pokémon pelo nome ou número e mostra seus dados na tela, consumindo a PokéAPI em tempo real.

## 1. Qual API foi usada

[PokéAPI](https://pokeapi.co/docs/v2) — documentação oficial em `https://pokeapi.co/docs/v2`.

## 2. O que ela devolve

Um objeto JSON com os dados do Pokémon consultado: `id`, `name`, `height` (altura), `weight` (peso), `types` (lista de tipos), `stats` (lista de atributos base como HP, ataque e defesa) e `sprites` (endereços de imagens do Pokémon).

## 3. O endereço que foi chamado

Consulta de exemplo (funciona direto no navegador):
`https://pokeapi.co/api/v2/pokemon/pikachu`

## 4. Como rodar

Abra o arquivo `index.html` diretamente no navegador (duplo clique ou clique com o botão direito → Abrir com). Não é necessário servidor, banco de dados, framework ou login. É necessário apenas estar conectado à internet, pois a página faz a requisição à PokéAPI a cada busca.

Digite o nome do Pokémon em inglês (ex.: `charizard`) ou o número dele na Pokédex (ex.: `6`) no campo de busca e clique em **Buscar**.

## 5. Print da tela funcionando

![Print da Pokédex funcionando, mostrando o resultado de uma busca por um Pokémon](print-funcionando.png)

*(Substitua a imagem acima pelo print real da sua tela após testar a busca, antes de enviar ao repositório.)*

## 6. Uma dificuldade que houve

A resposta da PokéAPI traz `types` e `stats` como **listas**, não como campos únicos — um Pokémon pode ter um ou dois tipos, e sempre tem seis atributos base dentro de um array. A primeira tentativa tentava ler `data.types.name` diretamente, como se fosse um único objeto, e retornava `undefined`. A solução foi percorrer a lista com `forEach`, acessando `t.type.name` para cada item, e montar os elementos na tela dinamicamente para cada tipo e cada atributo.
