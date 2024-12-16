# **Elicitação de Requisitos para o Projeto "S Text Editor"**

# **Histórico de Revisão**

| Data     | Versão | Descrição                                               | Autor          |
| -------- | ------ | ------------------------------------------------------- | -------------- |
| 11/12/24 | 1.0    | Elaboração para análise da primeria versão do documento | Diego Medeiros |
|          |        |                                                         |                |

# **Conteúdo**

## **1. Introdução**

### **1.1. Objetivo**

Este documento tem como finalidade identificar, documentar e detalhar os requisitos funcionais e não funcionais para o desenvolvimento do **S Text Editor**, um aplicativo de edição de texto leve e eficiente. A partir das informações coletadas, o objetivo é garantir que o sistema desenvolvido atenda às expectativas e necessidades dos usuários, além de fornecer uma base sólida para testes, implementação e manutenção.

### **1.2. Contexto**

O **S Text Editor** é um software destinado a usuários que necessitam de um editor de texto básico, com funcionalidades essenciais para a criação, edição e manipulação de documentos de texto. Seu público-alvo inclui estudantes, redatores e profissionais que procuram uma ferramenta leve, sem as complexidades de editores mais robustos, mas com um conjunto de funcionalidades essenciais para o trabalho cotidiano.

### **1.3. Metodologia de Elicitação**

A elicitação de requisitos foi realizada por meio da análise do Documento de Visão elaborado, de entrevistas com stakeholders-chave e estudo de concorrentes. O feedback foi coletado diretamente de um grupo de usuários potenciais, com o objetivo de identificar suas expectativas e prioridades para a ferramenta. As ferramentas e técnicas utilizadas incluem:

- Análise de documentos
- Entrevistas
- Prototipagem de interface
- Análise de concorrentes
- Levantamento de requisitos através de questionários

## **2. Requisitos Funcionais**

### _2.1. RF001 - Criação de Novo Documento_

- **Objetivo:** Permitir que o usuário crie um novo documento em branco.
- **Comportamento:** Ao selecionar a opção "Novo Documento", o sistema deve abrir uma nova área de texto em branco, pronta para ser editada.

### _2.2. RF002 - Abrir Documento Existente_

- **Objetivo:** Permitir que o usuário abra documentos previamente salvos no sistema de arquivos.
- **Comportamento:** O sistema deve permitir ao usuário navegar pelo sistema de arquivos e abrir um documento existente. O conteúdo do documento será exibido na área de edição.

### _2.3. RF003 - Editar Texto_

- **Objetivo:** O usuário pode inserir, excluir, copiar, colar e cortar texto no documento.
- **Comportamento:** O texto deve ser editável em tempo real, e o sistema deve fornecer suporte a atalhos de teclado e comandos para realizar essas ações.

### _2.4. RF004 - Salvar Documento_

- **Objetivo:** Permitir que o usuário salve o documento atual no formato `.txt`.
- **Comportamento:** O sistema deve solicitar ao usuário um local para salvar o arquivo atual ou sobrescrever o arquivo existente no sistema pela versão em edição, caso o usuário esteja editando um arquivo existente.

### _2.5. RF005 - Duplicar Documento_

- **Objetivo:** Permitir que o usuário duplique o documento atual com um novo nome (como "Documento Do Usuário - Cópia").
- **Comportamento:** O sistema deve solicitar ao usuário um novo local para salvar o documento atual e deve prover um nome padrão que seja diferente do atual, para evitar sobrescrição do arquivo já existente.

### _2.6. RF006 - Desfazer e Refazer_

- **Objetivo:** O usuário pode desfazer e refazer até 30 ações consecutivas.
- **Comportamento:** O sistema deve manter um histórico de ações e permitir ao usuário desfazer e refazer alterações em tempo real.

### _2.7. RF007 - Contagem de Linhas e Palavras_

- **Objetivo:** Exibir a contagem de linhas e palavras em tempo real.
- **Comportamento:** O número de palavras e linhas do documento deve ser atualizado automaticamente conforme o texto é modificado.

### _2.8. RF008 - Busca no Texto_

- **Objetivo:** Permitir que o usuário busque por palavras ou frases dentro do texto.
- **Comportamento:** O sistema deve localizar e destacar as palavras ou frases buscadas, permitindo a navegação entre as ocorrências encontradas.

### _2.9. RF009 - Ajuste de Tamanho de Fonte_

- **Objetivo:** Permitir ao usuário ajustar o tamanho da fonte do texto.
- **Comportamento:** O sistema deve fornecer controles para aumentar ou diminuir o tamanho da fonte, com valores entre 12px e 44px.

## **3. Requisitos Não Funcionais**

### _3.1. RNF002 - Desempenho_

- **Objetivo:** O sistema deve ser eficiente em termos de performance.
- **Comportamento:** O aplicativo deve ser capaz de carregar documentos de até 10 MB em menos de 2 segundos, e realizar operações de salvamento em até 1 segundo.

### _3.2. RNF004 - Confiabilidade_

- **Objetivo:** O sistema deve ser confiável, prevenindo a perda de dados.
- **Comportamento:** O sistema deve exibir mensagens claras em caso de erro e proteger os dados contra corrupção em caso de falhas.

### _3.3. RNF005 - Segurança_

- **Objetivo:** Garantir que os arquivos e dados do usuário sejam mantidos seguros.
- **Comportamento:** O sistema deve verificar a integridade dos arquivos ao abri-los e evitar abrir arquivos maliciosos.

### _3.4. RNF006 - Manutenibilidade_

- **Objetivo:** Facilitar a manutenção e evolução do software.
- **Comportamento:** O código do aplicativo será modular, e cada módulo será documentado e bem estruturado para permitir futuras modificações.

### _3.5. RNF007 - Acessibilidade_

- **Objetivo:** Garantir que o aplicativo seja acessível para todos os usuários, incluindo aqueles com deficiência.
- **Comportamento:** Todos os elementos interativos do aplicativo terão descrições e tooltips que expliquem sua funcionalidade.
