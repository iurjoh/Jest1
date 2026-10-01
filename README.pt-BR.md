# Jest1

Pequeno repositório de estudo de JavaScript para testes unitários e de DOM com Jest.

[English](README.md)

## Estado e registro do processo

Código revisado em 01/10/2026. O README original só tinha o nome do repositório. Não foram encontrados planejamento datado, wireframes ou diário de desenvolvimento nos arquivos revisados. Esta atualização descreve código e testes existentes, não uma calculadora completa ou aplicação de produção. Testes e demonstração no navegador não foram executados.

## Ideia, arquitetura e design

- `script/calc.js`: função de adição exportada.
- `script/button.js`: altera o parágrafo `#par` para "You Clicked" e exporta a função para testes CommonJS.
- `index.html`: título, botão "Click Me" e parágrafo vazio.
- `script/tests/calc.test.js`: uma asserção de adição; grupos de subtração, multiplicação e divisão são placeholders vazios.
- `script/tests/button.test.js`: testes jsdom que leem index.html, chamam a função exportada e verificam parágrafo e quantidade de títulos.

O design é uma página HTML mínima para teste, não um produto estilizado. Não há API ou banco nessa estrutura. package.json declara Jest `^26.6.3` como dependência de desenvolvimento e `npm test` executa Jest.

## Configuração e testes

Use ambiente local descartável com versão compatível de Node.js/npm. Dependências históricas precisam de revisão antes de reutilização.

```bash
npm ci
npm test
```

Três casos implementados: adição, atualização do parágrafo e existência do título. Não executados aqui; não se afirma aprovação ou percentual de cobertura. Os testes de DOM chamam a função diretamente e não comprovam carregamento do script ou clique no navegador real.

## Problemas conhecidos e próximos testes

`index.html` referencia `scripts/button.js`, mas o diretório real é `script/`. O arquivo também usa `module.exports`, exigindo contexto CommonJS ou tratamento adequado no navegador. A demonstração estática precisa de revisão antes de ser apresentada como funcional. Nenhum código foi alterado para esconder esses problemas.

Antes de reutilizar, verifique caminho do script, diferença entre navegador e módulos, clique real e comportamento de entradas numéricas. Implemente e teste outras operações se desejado. O `node_modules/` versionado não substitui instalação limpa pelo manifest e lockfile.

## Capturas

Nenhuma captura de aplicação foi verificada ou adicionada. Depois de corrigir e verificar a demonstração, capture estados inicial e após clique em arquivos datados sob `docs/assets/`, sem dados pessoais. Capturas de testes devem mostrar comando e resultado reais. Só adicione links após os arquivos existirem.

## Créditos e licença

O manifest existente declara ISC; declaração preservada, sem adicionar arquivo de licença. Jest e dependências mantêm suas licenças. Este README não afirma autoria original de material de exercício de terceiros cuja origem não esteja estabelecida nos arquivos revisados.
