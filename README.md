# Painel de Câmbio

Dashboard web que exibe cotações de moedas em tempo real, consumindo uma API pública — projeto de portfólio focado em consumo de dados externos (fetch, tratamento de erro de rede, exibição assíncrona).

## O que ele faz

- **Conversor de moedas**: digite um valor, escolha a moeda de origem e destino (entre Real, Dólar, Euro, Libra e outras), e veja a conversão calculada com a cotação do momento
- **Cotações em destaque**: Dólar, Euro e Libra — as moedas mais consultadas — em cartões de leitura rápida
- **Tabela completa do dia**: compra, venda, mínima, máxima e variação percentual de 9 moedas frente ao Real (Dólar, Euro, Libra, Dólar canadense, Dólar australiano, Franco suíço, Iene, Peso argentino e Bitcoin)
- **Histórico com período selecionável**: 7, 30, 90 ou 180 dias, em gráfico de linha, para qualquer uma das moedas
- Atualiza as cotações automaticamente a cada 2 minutos
- Trata falhas de rede com uma mensagem clara e botão de tentar de novo

## Tecnologia

Arquivo único em HTML, CSS e JavaScript puro (sem frameworks, sem build), com [Chart.js](https://www.chartjs.org/) para o gráfico. Os dados vêm da [AwesomeAPI](https://docs.awesomeapi.com.br/api-de-moedas), uma API brasileira gratuita de cotações — sem necessidade de cadastro ou chave de acesso.

Como toda a lógica roda no navegador de quem acessa (o próprio JavaScript da página faz a chamada à API), basta abrir o arquivo ou hospedar em qualquer serviço de páginas estáticas — não precisa de servidor.


## API utilizada

[AwesomeAPI — API de Cotações](https://docs.awesomeapi.com.br/api-de-moedas)

Endpoints usados:
- `GET /json/last/:moedas` — cotação mais recente de uma ou mais moedas
- `GET /json/daily/:moeda/:dias` — histórico dos últimos N dias de uma moeda

Sem chave de API, requisições não autenticadas ficam em cache por 1 minuto (por isso a página atualiza a cada 2 minutos, em vez de constantemente).

## Autoria

Pedro Costa Barroso.
Projeto acadêmico/portfólio, sem fins comerciais.
