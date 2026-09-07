<div align="center">

<img src="assets/logo.png" width="110" alt="Logo TESOURO IR" />

# TESOURO IR

### Controle de Dados para Declaração do Imposto de Renda

Uma planilha Excel interativa para organizar, validar e consolidar todas as informações necessárias antes de preencher a declaração do IRPF — com navegação por botões, validação de dados e um painel de resumo calculado automaticamente.

![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Status](https://img.shields.io/badge/status-concluído-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/licença-MIT-blue?style=for-the-badge)

</div>

---

## 📌 Sobre o projeto

O **TESOURO IR** nasceu de um problema simples e recorrente: todo ano, na época da declaração do Imposto de Renda, é preciso reunir CPF, informes de rendimentos bancários, comprovantes e uma dúzia de outros dados espalhados em e-mails, PDFs e anotações soltas.

Este projeto propõe uma solução prática dentro do próprio Excel — sem plugins, sem macros e sem depender de nenhum serviço externo. É uma planilha inteligente que funciona como um **mini sistema de organização fiscal pessoal**, com:

- navegação entre seções por botões clicáveis (como se fossem "abas" de um app);
- campos de preenchimento com validação (listas suspensas, formatos de CPF/CEP/telefone);
- uma tabela dinâmica para lançamentos mensais de receita;
- um painel de resumo que consolida tudo automaticamente com fórmulas.

O objetivo é ser, ao mesmo tempo, uma ferramenta útil no dia a dia e um exemplo de boas práticas de modelagem de planilhas (dados de entrada separados de fórmulas, listas de apoio ocultas, formatação condicional, tabelas estruturadas).

> ⚠️ **Aviso importante:** esta planilha é uma ferramenta de **organização pessoal de dados**. Ela não envia, transmite nem calcula o imposto devido — o preenchimento oficial da declaração continua sendo feito no programa da Receita Federal (ou similar do seu país). Todos os dados usados como exemplo neste repositório são fictícios.

---

## 🖼️ Demonstração

<table>
<tr>
<td width="50%">

**1. Dados do Titular**
<img src="assets/screenshots/titular.png" alt="Aba Titular" />

</td>
<td width="50%">

**2. Informes de Rendimentos**
<img src="assets/screenshots/rendimentos.png" alt="Aba Rendimentos" />

</td>
</tr>
<tr>
<td width="50%">

**3. Lançamentos Mensais**
<img src="assets/screenshots/lancamentos.png" alt="Aba Lançamentos" />

</td>
<td width="50%">

**4. Resumo Geral**
<img src="assets/screenshots/resumo.png" alt="Aba Resumo" />

</td>
</tr>
</table>

---

## ✨ Funcionalidades

- 🧭 **Navegação facilitada** — menu lateral fixo com botões que levam direto para cada aba (hyperlinks internos), além de botões "Anterior / Próximo" no rodapé de cada seção.
- ✅ **Validação de dados** — campos como "SIM/NÃO", banco e categoria da receita usam listas suspensas, evitando erros de digitação e inconsistências.
- 🏦 **Lista de bancos pré-carregada** — mais de 50 instituições financeiras brasileiras (com código COMPE) disponíveis para seleção rápida no informe de rendimentos.
- 📊 **Tabela estruturada (Excel Table)** — os lançamentos mensais usam uma Tabela do Excel de verdade, com filtros automáticos e fácil expansão de linhas.
- 🧮 **Fórmulas 100% dinâmicas** — nenhum valor de total é fixo; tudo é recalculado automaticamente com `SOMA`, `SOMASE` e `ÍNDICE`/`CORRESP`.
- 📈 **Painel de resumo com barras de dados** — visualização rápida de quanto cada categoria representa no total de receitas, com formatação condicional.
- 🎨 **Identidade visual própria** — paleta de cores, tipografia e logo consistentes em todas as abas.
- 🔒 **Lista de apoio protegida** — a aba `LISTAS`, que alimenta os menus suspensos, fica oculta para não atrapalhar o uso do dia a dia.

---

## 🗂️ Estrutura da planilha

| Aba | Visibilidade | Conteúdo |
|---|---|---|
| `TITULAR` | Visível | Dados pessoais do declarante (nome, CPF, endereço, contatos, situação cadastral) |
| `RENDIMENTOS` | Visível | Até 3 informes de rendimentos bancários, com banco, valor atual, anexo e total automático |
| `LANCAMENTOS` | Visível | Tabela de entradas de receita mês a mês, por data, categoria e valor |
| `RESUMO` | Visível | Totais consolidados e receitas agrupadas por categoria |
| `LISTAS` | Oculta | Listas de apoio (bancos, categorias, SIM/NÃO) usadas pelas validações de dados |

### Fluxo de navegação

```
TITULAR  →  RENDIMENTOS  →  LANÇAMENTOS  →  RESUMO
   ↑____________↑______________↑_____________↓
                 (menu lateral disponível em todas as abas)
```

---

## 🚀 Como usar

1. Baixe o arquivo [`TESOURO_IR_Controle_Declaracao.xlsx`](./TESOURO_IR_Controle_Declaracao.xlsx) deste repositório.
2. Abra no **Microsoft Excel** (recomendado) ou em outra suíte compatível, como LibreOffice Calc ou Google Sheets (algumas formatações visuais podem variar fora do Excel).
3. Na aba `TITULAR`, substitua os dados de exemplo pelos seus próprios dados.
4. Navegue até `RENDIMENTOS` usando o botão do menu lateral (ou o botão **PRÓXIMO →**) e preencha os informes bancários do ano.
5. Em `LANÇAMENTOS`, adicione uma linha para cada entrada de receita do período (a tabela se expande automaticamente).
6. Consulte a aba `RESUMO` para ver os totais e a distribuição por categoria já calculados.
7. Use esses dados consolidados como checklist na hora de preencher sua declaração no programa oficial.

### Campos com preenchimento assistido

| Campo | Tipo de assistência |
|---|---|
| CPF, CEP, telefone e celular | Máscara de formatação automática |
| Data de nascimento / datas de lançamento | Formato de data `dd/mm/aaaa` |
| Alterações da entrega anterior / dependente cônjuge / residente no exterior | Lista suspensa (SIM / NÃO) |
| Banco (em `RENDIMENTOS`) | Lista suspensa com bancos brasileiros |
| Categoria (em `LANÇAMENTOS`) | Lista suspensa (Salário, Freelance, Aluguel, Investimentos, Outros) |

---

## 🛠️ Tecnologias e conceitos aplicados

- **Microsoft Excel** (formato `.xlsx`, compatível com Excel 2016+)
- Fórmulas: `SOMA`, `SOMASE`, `ÍNDICE`, `CORRESP`, `MÁXIMO`
- **Validação de Dados** (listas suspensas dinâmicas)
- **Tabelas Estruturadas** do Excel (`Tabela1`) com referências estruturadas (`Tabela[Coluna]`)
- **Formatação Condicional** (barras de dados)
- **Hyperlinks internos** para navegação entre abas
- Formatos de número customizados (CPF, CEP, telefone, moeda)
- Planilha auxiliar oculta para separar dados de apoio da interface do usuário

---

## 🎨 Personalização

Quer adaptar o modelo à sua própria marca? Os principais pontos de customização são:

- **Cores** — a paleta principal (verde `#0B3D2E` e dourado `#C9A227`) é aplicada nos preenchimentos de célula e fontes; basta substituir os códigos de cor nas células de título, menu lateral e botões.
- **Logo** — troque a imagem inserida no canto superior do menu lateral por sua própria logomarca (formato PNG com fundo transparente funciona melhor).
- **Categorias e bancos** — edite a aba oculta `LISTAS` para adicionar, remover ou renomear os itens das listas suspensas.
- **Novas seções** — é possível duplicar o padrão de uma aba existente (título, subtítulo, menu lateral) para criar novas seções, como "Deduções" ou "Bens e Direitos".

---

## 🗺️ Possíveis melhorias futuras

- [ ] Aba de bens e direitos com cálculo de variação patrimonial
- [ ] Aba de despesas dedutíveis (saúde, educação, previdência)
- [ ] Exportação automática de um resumo em PDF
- [ ] Versão para dependentes (múltiplos titulares)

Contribuições e sugestões são bem-vindas — sinta-se à vontade para abrir uma *issue* ou um *pull request*.

---

## 📄 Licença

Este projeto está disponível sob a licença [MIT](./LICENSE). Sinta-se livre para usar, adaptar e distribuir, mantendo os devidos créditos.

---

<div align="center">

Feito com 💚 para facilitar a organização fiscal de cada ano.

</div>
