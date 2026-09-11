# Simulador de Investimentos em Fundos Imobiliários (FIIs)

Simulador de investimentos em FIIs feito em Excel: informe valor inicial, aporte mensal e taxa de rendimento e veja a evolução do seu patrimônio mês a mês.

> Projeto desenvolvido como desafio de código do bootcamp **Digital Innovation One (DIO)**, aplicando conceitos de Excel para automatizar cálculos financeiros de simulação de investimentos.

## 🎯 Objetivo

Fundos Imobiliários (FIIs) são um dos investimentos mais populares entre investidores brasileiros, mas quem está começando costuma ter as mesmas dúvidas: *quanto investir?*, *por quanto tempo?*, *qual retorno esperar?*, *vale a pena reinvestir os dividendos?*.

Esta planilha automatiza essas contas: a partir de alguns parâmetros de entrada, ela calcula o valor total investido, o patrimônio acumulado ao longo do tempo e os dividendos mensais recebidos, mês a mês, ajudando a visualizar o potencial retorno do investimento.

## 📁 Estrutura do repositório

```
simulador-investimentos-fii-excel/
├── README.md
├── Simulador_Investimentos_FII.xlsx
└── images/
    ├── aba-simulador.png
    └── aba-evolucao-mensal.png
```

## 📊 Como usar a planilha

A planilha tem duas abas:

### 1. Aba `Simulador`

É onde você preenche os dados da sua simulação (células em **amarelo**) e visualiza o resultado.

**Parâmetros de entrada:**

| Parâmetro | Descrição |
|---|---|
| Valor Inicial Investido | Valor aportado no fundo no mês 0, antes de qualquer aporte mensal |
| Aporte Mensal | Valor investido todo mês, além do valor inicial |
| Taxa de Rendimento Mensal (%) | Dividend yield mensal médio esperado do FII (consulte o histórico de dividendos do fundo para estimar) |
| Prazo da Simulação (meses) | Por quantos meses o investimento será mantido |
| Reinvestir Dividendos? (Sim/Não) | Se "Sim", os dividendos recebidos são somados ao patrimônio (juros compostos); se "Não", ficam acumulados separadamente, como se fossem sacados |

**Resultado calculado automaticamente:**

- Total Investido (aportes)
- Patrimônio Acumulado ao Final do Prazo
- Total de Dividendos Recebidos no Período
- Saldo em Caixa (dividendos não reinvestidos)
- Retorno Total sobre o Investido (%)

### 2. Aba `Evolução Mensal`

Detalha a simulação mês a mês (preparada para até 60 meses), mostrando para cada mês:

- Patrimônio no início e no final do mês
- Aporte do mês
- Dividendo do mês
- Reinvestimento do mês
- Dividendos e caixa acumulados
- Total investido acumulado

Essa aba também traz um **gráfico de linha** comparando a evolução do patrimônio acumulado com o total investido, deixando visual o efeito dos juros compostos.

> Para simular prazos maiores que 60 meses, basta selecionar a última linha da tabela e arrastar/copiar as fórmulas para baixo.

## 🧮 Lógica dos cálculos

Para cada mês da simulação:

```
Dividendo do Mês        = Patrimônio no Início do Mês × Taxa de Rendimento Mensal
Reinvestimento do Mês   = Dividendo do Mês, se "Reinvestir Dividendos" = Sim; senão 0
Patrimônio Final do Mês = Patrimônio no Início do Mês + Aporte do Mês + Reinvestimento do Mês
```

Os valores acumulados (dividendos recebidos, caixa não reinvestido e total investido) são somados progressivamente mês a mês, e o resumo na aba `Simulador` busca o valor correspondente ao mês definido em "Prazo da Simulação".

Todas as células de resultado usam **fórmulas nativas do Excel** (nunca valores fixos), então a planilha recalcula automaticamente sempre que um parâmetro de entrada é alterado.

## 🛠️ Conceitos e ferramentas aplicados

- Fórmulas financeiras e de busca (`INDEX`, `MATCH`, `IF`, `SUM`)
- Referências relativas e absolutas entre abas
- Formatação condicional de células (entradas x resultados)
- Gráficos dinâmicos no Excel
- Documentação técnica em Markdown
- Versionamento e publicação com Git/GitHub

## 📚 Aprendizados

Este desafio permitiu aplicar na prática:

- Como estruturar uma planilha de simulação financeira de forma clara, separando entradas, cálculos e resultados
- Como montar fórmulas encadeadas mês a mês para simular a evolução de um investimento com juros compostos
- Como transformar um problema real de investidores de FIIs em uma ferramenta prática e reutilizável
- Como documentar um processo técnico de forma estruturada, para que qualquer pessoa consiga entender e usar o projeto

## 📸 Capturas de tela

*(adicionar prints das abas `Simulador` e `Evolução Mensal` na pasta `/images`)*

## 👤 Autor

Desenvolvido por **Yamaia**, como parte da trilha de estudos da Digital Innovation One (DIO).
