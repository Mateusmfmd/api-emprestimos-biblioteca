# api-emprestimos-biblioteca
[![CI](https://github.com/Mateusmfmd/api-emprestimos-biblioteca/actions/workflows/ci.yml/badge.svg)](https://github.com/Mateusmfmd/api-emprestimos-biblioteca/actions/workflows/ci.yml)

Domínio de uma biblioteca em Java 21 com regras de negócio para cadastro de livro, empréstimo, reserva, devolução, prazo e multa. A primeira versão é deliberadamente sem framework e sem banco externo para deixar as regras testáveis e fáceis de estudar.

## Regras

- Livro inexistente não pode ser emprestado.
- Livro com empréstimo aberto não pode ser reservado por outra pessoa.
- Empréstimo calcula prazo em dias.
- Multa é de R$ 2 por dia de atraso.
- Devolução encerra o empréstimo.

## Testar

```bash
mkdir -p build
javac -d build src/main/java/br/com/mateus/biblioteca/Library.java tests/LibraryTest.java
java -ea -cp build LibraryTest
```

## Próximos passos

Adicionar API HTTP, persistência e autenticação quando as regras de domínio estiverem estáveis.

MIT — Mateus Florido Pena
