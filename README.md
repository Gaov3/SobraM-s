# SobraMês — Gestão Financeira Visual

> Projeto Final desenvolvido para a disciplina de **Engenharia de Software** do **Centro Universitário de Maceió (UNIMA)**.

## 📌 Sobre o Projeto
O **SobraMês** é uma aplicação web simples, responsiva e intuitiva desenvolvida para resolver a falta de clareza na distribuição do salário mensal. Sem exigir cadastros complexos, servidores externos ou integração bancária, o sistema permite gerenciar múltiplos controles financeiros independentes, calcular quanto cada despesa consome do salário (em R$ e %) e visualizar a distribuição do orçamento em um gráfico de rosca/pizza atualizado em tempo real.

## 🎯 Problema que Resolve
Muitas pessoas com renda mensal (trabalhadores, estagiários e estudantes) chegam ao fim do mês sem saber para onde o dinheiro foi, pois planilhas tradicionais e aplicativos financeiros costumam ser excessivamente complexos. O **SobraMês** oferece uma visão imediata de quanto cada gasto compromete do orçamento e quanto ainda resta livre.

## ⚡ Principais Funcionalidades
- **RF01 — Gestão de Salário Mensal:** Inserção e atualização dinâmica do salário base de cada controle.
- **RF02 — Cadastro de Gastos com Percentual:** Registro de despesas com nome, valor (R$), cor personalizada e cálculo automático da porcentagem consumida do salário (`% Salário`).
- **RF03 — Gráfico de Pizza Dinâmico:** Renderização interativa (Chart.js) atualizada instantaneamente a cada alteração, sem recarregar a página.
- **RF04 — Edição e Exclusão de Gastos:** Atualização rápida ou remoção de despesas diretamente na tabela.
- **RF05 — Saldo Livre e Alerta de Déficit:** Exibição do saldo restante (em R$ e %) com alerta visual automático caso os gastos ultrapassem o salário mensal.
- **RF06 / RNF03 — Persistência Local e Múltiplos Controles:** Aba lateral esquerda para criar, alternar, renomear e excluir diferentes controles de gastos (ex.: meses distintos ou metas específicas), armazenados localmente no navegador via `localStorage`.

## 🛠️ Tecnologias Utilizadas
- **HTML5:** Estruturação semântica da interface.
- **CSS3:** Estilização moderna e layout responsivo para desktop e dispositivos móveis (RNF01).
- **JavaScript (ES6+):** Regras de negócio, cálculos percentuais, gerenciamento de múltiplos orçamentos e manipulação dinâmica do DOM.
- **Chart.js:** Visualização gráfica interativa da distribuição financeira em tempo real (RNF02).
- **LocalStorage API:** Armazenamento persistente no próprio navegador do usuário (RNF03).

## 🚀 Como Executar o Projeto
Como a aplicação é 100% *client-side*, não é necessário instalar servidores, bancos de dados ou dependências externas:

1. Clone este repositório ou faça o download dos arquivos em `.zip`:
   ```bash
   git clone https://github.com/Gaov3/SobraM-s.git
   ```
2. Acesse a pasta do projeto.
3. Abra o arquivo `index.html` (ou `SobraMês.html`) diretamente em qualquer navegador web moderno (Google Chrome, Microsoft Edge, Firefox ou Safari).

## 📂 Documentação e Capturas de Tela
Os diagramas UML (Casos de Uso e Diagrama de Classes), as capturas de tela do sistema em funcionamento e as evidências do quadro Kanban estão disponíveis na pasta [`/Docs`](./Docs) deste repositório.

## 📊 Gestão do Projeto (Trello)
O planejamento e o acompanhamento das entregas foram conduzidos sob o modelo **Ágil Incremental com Kanban** (colunas: *A fazer*, *Em andamento*, *Testes* e *Concluído*):

- **Quadro Trello (Acesso Público / Observador):** [Acessar Quadro SobraMês no Trello](https://trello.com/invite/b/6af49186a36348cb968e19b4/ATTI00c829be0a45663523844700a6e57c905DEA1026/💰-projeto-de-software-controle-financeiro)

## 🧪 Casos de Teste Validados

| ID | Funcionalidade Testada | Procedimento Realizado | Resultado Esperado | Situação |
| :--- | :--- | :--- | :--- | :--- |
| **CT01** | Definir Salário e Saldo Livre (RF01, RF05) | Informar `3500` no campo Salário Mensal e salvar. | Saldo livre exibe R$ 3.500,00 (100,0% livre). | **Aprovado** |
| **CT02** | Cadastrar Gastos e Gráfico (RF02, RF03) | Cadastrar Aluguel (R$ 1.200), Mercado (R$ 650) e Transporte (R$ 300). | Tabela exibe valores e percentuais (34,3%, 18,6%, 8,6%) e gráfico atualiza em tempo real. | **Aprovado** |
| **CT03** | Alerta de Déficit Orçamentário (RF05) | Adicionar gasto de R$ 1.600 ultrapassando o salário de R$ 3.500. | Alerta vermelho é exibido e saldo livre fica negativo (-R$ 250,00). | **Aprovado** |
| **CT04** | Múltiplos Controles e Persistência (RF06) | Criar novo controle na barra lateral, alternar entre eles e reabrir o navegador. | Controles permanecem isolados e salvos via `localStorage`. | **Aprovado** |

## 👨‍💻 Equipe de Desenvolvimento e Divisão de Papéis
- **Lucas Camilo:** Desenvolvimento front-end (HTML5/CSS3/JavaScript), aba lateral de múltiplos controles, integração com Chart.js e persistência via `localStorage`.
- **Caio Ronaldo:** Levantamento de requisitos (Google Forms), especificação de RFs/RNFs e elaboração/execução dos casos de teste.
- **Maria Tereza:** Modelagem UML (Diagramas de Casos de Uso e de Classes) e prototipação de interfaces.
- **Gabriel Alexandre:** Gestão do projeto no Trello (Kanban), organização da documentação no GitHub e consolidação do relatório técnico em PDF.
