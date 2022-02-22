# Starwars Planets Search

Foi desenvolvido uma lista com filtros de planetas do universo de Star Wars usando **Context API e Hooks**<br/>
Projeto desenvolvido durante o curso de Desenvolvimento Web Full Stack da Trybe
# Tecnologias usadas

![Javascript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)<br/>
API Star Wars Planets - consulte [nesse link](https://swapi-trybe.herokuapp.com/api/planets/)

# Desenvolvimento
1. Clone o repositório
2. Instale as dependências e inicialize o projeto
  * Instale as dependências:
    * `npm install`
  * Inicialize o projeto:
    * `npm start`
# Requisitos do projeto

## Lista de requisitos(Propostos pela Trybe)

### 1 - Faça uma requisição para o endpoint `/planets` da API de Star Wars e preencha uma tabela com os dados retornados, com exceção dos da coluna `residents`

![image](req-1.png)


### 2 - Filtre a tabela através de um texto, inserido num *campo de texto*, exibindo somente os planetas cujos nomes incluam o texto digitado

```javascript
{
  filters: {
    filterByName: {
      name: 'Tatoo'
    }
  }
}
```
![img](req-2.gif)

### 3 - Crie um filtro para valores numéricos

Ele funcionará com três seletores:

  - O primeiro deve abrir um dropdown que permita a quem usa selecionar uma das seguintes colunas: `population`, `orbital_period`, `diameter`, `rotation_period` e `surface_water`. Deve ser uma tag `select`;
  - O segundo deve determinar se a faixa de valor será `maior que`, `menor que` ou `igual a` o numero que virá a seguir. Uma tag `select`;
  - O terceiro deve ser uma caixa de texto que só aceita números. Essa caixa deve ser uma tag `input`;
  - Deve haver um botão para acionar o filtro`.

A combinação desses três seletores deve filtrar os dados da tabela de acordo com a coluna correspondente e com os valores escolhidos. Por exemplo:
  - A seleção `population | maior que | 100000` - Seleciona somente planetas com mais de 100000 habitantes.

```javascript
{
  filters:
    {
      filterByName: {
        name: ''
      },
      filterByNumericValues: [
        {
          column: 'population',
          comparison: 'maior que',
          value: '100000',
        }
      ]
    }
  }
}
```
![img](req-3.gif)

### 4 - Não utilize filtros repetidos

Caso um filtro seja totalmente preenchido, um novo filtro de valores numéricos deve ser carregado. Este novo filtro não deve incluir quaisquer colunas que já tenham sido selecionadas em filtros de valores numéricos anteriores. Caso todas as colunas já tenham sido inclusas em filtros anteriores, não deve ser carregado um novo filtro.

Por exemplo: O primeiro filtro tem as seguintes seleções: `population | maior que | 100000`. Um segundo filtro deve aparecer após essas seleções serem todas feitas e, no primeiro dropdown deste segundo filtro, a opção `population` deve estar ausente. Se no segundo filtro fosse selecionado `diameter | menor que | 8000`, o estado ficaria assim:

```javascript
{
  filters: {
    filterByName: {
      name: ''
    },
    filterByNumericValues: [
      {
        column: 'population',
        comparison: 'maior que',
        value: '100000',
      },
      {
        column: 'diameter',
        comparison: 'menor que',
        value: '8000',
      }
    ]
  }
}
```

![img](req-4.gif)

### 5 - Apague o filtro de valores numéricos e desfaça as filtragens dos dados da tabela ao clicar no ícone de `X` de um dos filtros

A coluna que este filtro selecionava deve passar a ficar disponível nos dropdowns dos demais filtros já presentes na tela.

![img](req-5.gif)

### 6 - Ordene as colunas de forma ascendente ou descendente

Essa ordenação deve ser feita via filtro: um dropdown selecionará a coluna a basear a ordenação e um par de radio buttons determinará se esta é ascendente ou descendente.

![img](req-6.gif)
