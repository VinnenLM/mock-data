# Mock-data

**Gerador de valores** fictícios brasileiros para testes e desenvolvimento. Roda inteiramente no navegador: nada é enviado para servidor.

**Demo:** https://vinnenlm.github.io/mock-data/

## O que gera

| Grupo | Geradores |
| --- | --- |
| Documentos | CPF, CNPJ (numérico e alfanumérico), RG, Inscrição Estadual, CNH, PIS/NIS, Título de eleitor |
| Pessoais | Nome, telefone, e-mail, data de nascimento, CEP, endereço, placa de veículo (antiga e Mercosul) |
| Financeiro | Conta bancária, cartão de crédito (Visa, Mastercard, Amex, Elo e Hipercard) |
| Combo | Pessoa completa, com os campos que você marcar |
| Ferramentas | Validador de CPF, CNPJ, cartão de crédito e Inscrição Estadual |

### Recursos

- Quantidade configurável (de 1 a 1000, padrão 1) e opção de gerar **com ou sem pontuação**.
- Opções por gerador: UF, bandeira do cartão, tipo de telefone, padrão da placa, campos do cartão (nome, número, validade, CVV, CPF do titular) etc.
- Clique em qualquer célula para copiar o valor. Também dá para **copiar tudo** ou baixar em **CSV** e **JSON**.
- **Pessoa completa** gera um perfil coerente: o e-mail é derivado do nome, e o CPF, o CEP e o endereço seguem a mesma UF.
- **Validador**: cole valores (um por linha) e veja se os dígitos verificadores conferem, com o motivo quando não conferem. Para cartões, identifica também a bandeira.
- Tema claro/escuro automático e layout responsivo.

## Sobre a validade dos dados

Os documentos são gerados com **dígitos verificadores válidos**, mas são **fictícios**: não significa que existam nem que pertençam a alguém.

- **CNPJ alfanumérico**: segue o formato em vigor desde julho de 2026.
- **Inscrição Estadual**: disponível para 23 UFs (AL, AM, BA, CE, DF, ES, GO, MA, MG, MS, MT, PA, PB, PE, PI, PR, RJ, RN, RR, RS, SC, SE e SP). AC, AP, RO e TO ainda não são suportadas.
- **RG**: não existe regra nacional única. Usa o padrão de 8 dígitos com dígito verificador em módulo 11.
- **CEP e endereço**: o CEP fica na faixa da UF, mas a combinação rua/CEP não existe de verdade.
- **Conta bancária**: estrutura fictícia (banco, agência, conta). O dígito não segue a regra de um banco específico.
- **Cartão de crédito**: passa no algoritmo de Luhn, mas é fictício e **não funciona em compras**. Para testar pagamentos, use os cartões de teste oficiais do seu gateway.
- **E-mail**: usa apenas domínios reservados (`example.com`, `example.org` e `example.net`).

## Privacidade

Todo o processamento acontece localmente, com JavaScript no navegador. Não há back-end, requisições externas nem armazenamento de dados.

## Como usar localmente

É um único arquivo, sem dependências nem build:

```bash
git clone https://github.com/VinnenLM/mock-data.git
cd mock-data
# abra o index.html no navegador
```

## Publicação

Como é um site estático, pode ser hospedado em qualquer serviço do tipo (GitHub Pages, Netlify, Cloudflare Pages etc.), sem back-end. Este projeto usa o **GitHub Pages**, a partir da branch `main`.

## Tecnologias

HTML, CSS e JavaScript puros.
