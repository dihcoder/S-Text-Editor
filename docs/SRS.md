# **Software Requirements Specification - "S Text Editor"**

> Documento de Especificação de Requisitos de Software do S Text Editor

## **Histórico de Revisão**

| Data     | Versão | Descrição                                  | Autor          |
| -------- | ------ | ------------------------------------------ | -------------- |
| 16/12/24 | 1.0    | Elaboração da primeria versão do documento | Diego Medeiros |
|          |        |                                            |                |

## **1. Introdução**

### **1.1. Propósito**

Este documento especifica os requisitos funcionais e não funcionais do **S Text Editor**, um aplicativo de edição de texto. Ele serve como referência principal para desenvolvimento, testes, manutenção e validação do software, garantindo que as funcionalidades atendam às necessidades dos usuários.

### **1.2. Escopo**

O S Text Editor será uma aplicação desktop para edição de texto com funcionalidades essenciais, como criar, abrir, editar, salvar e buscar textos. O sistema será compatível com os principais sistemas operacionais (Windows, macOS e Linux) e focado em simplicidade, desempenho e acessibilidade. O formato suportado será exclusivamente .txt.

### **1.3. Definições, Acrônimos e Abreviações**

- **S Text Editor:** Nome do projeto.
- **MVC:** Model-View-Controller, padrão de arquitetura utilizado no sistema.
- **RF:** Requisito Funcional
- **RNF:** Requisito Não Funcional
- **I/O:** Input/Output (Entrada/Saída)

### **1.4. Referências**

- Documento de Visão do Projeto: [`Vision.md`](./Vision.md)
- Documento de Design do Projeto: [`Design.md`](./Design.md)
- Documentação do JavaFX: [`https://openjfx.io`](https://openjfx.io/javadoc/23/)

## **2. Descrição Geral**

### **2.1. Funções Principais**

1. Criação, abertura e salvamento de documentos.
2. Edição de texto com suporte a desfazer/refazer.
3. Alteração de tamanho de fonte.
4. Contagem de linhas e palavras.
5. Busca de fragmentos de texto no documento.

### **2.2 Benefícios para os Usuários**

- **Usuários Finais:** Acesso a uma ferramenta leve e eficiente para tarefas cotidianas de edição de texto.
- **Equipe de Desenvolvimento:** Um sistema modular e bem documentado, que facilita a manutenção e a evolução.

### **2.3 Restrições Gerais**

- O sistema será desenvolvido exclusivamente como uma aplicação desktop.
- A aplicação deve ser leve, usando no máximo 100MB de memória em operação padrão, e rápida, carregando em menos de 2 segundos em sistemas modernos.
- A aplicação deve suportar edição de documentos de até 1 milhão de caracteres.
- O suporte inicial será limitado ao formato de arquivo .txt.
- Deve ser compatível com Java 17 e versões posteriores.

## **3. Requisitos Funcionais**

### _3.1. RF001 - Criação de Novo Documento:_

- **Descrição:** O sistema deve permitir ao usuário criar um novo documento em branco.
- **Entrada:** Comando do usuário (menu, botão ou atalho de teclado).
- **Processamento:** Limpar a área de texto e exibir um título padrão.
- **Saída:** Área de texto em branco exibida com o título "Novo Documento - S Text Editor".

### _3.2. RF002 - Abrir Documento:_

- **Descrição:** O sistema deve permitir ao usuário abrir um documento existente.
- **Entrada:** Comando do usuário (menu, botão ou atalho de teclado).
- **Processamento:** Carregar o conteúdo do documento selecionado.
- **Saída:** Conteúdo do documento exibido na área de texto.

### _3.3. RF003 - Editar Texto:_

- **Descrição:** O sistema deve permitir ao usuário inserir, editar, excluir, recortar, copiar e colar texto no documento.
- **Entrada:** Ações do usuário (digitação, seleção, cópia, recorte, colagem, exclusão).
- **Processamento:** Atualizar o conteúdo da área de texto conforme a entrada do usuário.
- **Saída:** Texto atualizado exibido na área de texto.

### _3.4. RF004 - Salvar Documento:_

- **Descrição:** O sistema deve permitir ao usuário salvar o documento atual no formato .txt.
- **Entrada:** Comando do usuário (menu, botão ou atalho de teclado).
- **Processamento:** Salvar o conteúdo do documento no local especificado.
- **Saída:** Confirmação de salvamento bem-sucedido.

### _3.5. RF005 - Duplicar Documento:_

- **Descrição:** O sistema deve permitir ao usuário salvar o documento atual com um novo nome ou local no formato .txt.
- **Entrada:** Comando do usuário (menu, botão ou atalho de teclado).
- **Processamento:** Solicitar ao usuário um novo nome e/ou local para o arquivo e salvar o conteúdo.
- **Saída:** Confirmação de salvamento bem-sucedido.

### _3.6. RF006 - Ajuste de Tamanho do Texto_

- **Descrição:** O sistema deve permitir ao usuário aumentar ou diminuir o tamanho da fonte do texto no intervalo de 12px a 44px.
- **Entrada:** Comando do usuário (interação com o controle deslizante ou uso de atalhos de teclado)
- **Processamento:** Alterar, em tempo real, o tamanho da fonte exibida na área de texto.
- **Saída:** Texto exibido com o novo tamanho de fonte.

### _3.7. RF007 - Desfazer e Refazer:_

- **Descrição:** O sistema deve permitir ao usuário desfazer e refazer até 30 alterações consecutivas no texto.
- **Entrada:** Comando do usuário (menu, botão ou atalho de teclado).
- **Processamento:** Desfazer ou refazer uma alteração por vez.
- **Saída:** Texto modificado conforme o histórico de alterações.

### _3.8. RF008 - Busca no Texto:_

- **Descrição:** O sistema deve permitir ao usuário buscar por palavras ou frases específicas no documento. Após realizar a busca, o sistema deve destacar a primeira ocorrência encontrada no texto e possibilitar a navegação para as próximas e anteriores correspondências através de botões ou atalhos de teclado.
- **Entrada:** Texto ou frase fornecido pelo usuário para busca.
- **Processamento:** Localizar todas as ocorrências do texto ou frase buscados no documento e destacar a primeira ocorrência inicialmente.
- **Saída:** Primeira correspondência destacada na área de texto, com possibilidade de navegar entre todas as correspondências encontradas.
- **Erro:** Se nenhuma correspondência for encontrada, exibir mensagem "Nada foi encontrado!".

### _3.9. RF009 - Contagem de Linhas e Palavras:_

- **Descrição:** O sistema deve permitir ao usuário acompanhar, em tempo real, a quantidade de linhas e palavras que compõem o documento.
- **Entrada:** Atualizações do conteúdo da área de texto.
- **Processamento:** Realizar a contagem de linhas e palavras da área de texto.
- **Saída:** Quantidade de linhas e palavras exibidas no rodapé, dinamicamente.

### _3.10. RF010 - Barra de Ferramentas_

- **Descrição:** O sistema deve possuir uma barra de ferramentas com as opções principais: Arquivo, Editar, Desfazer, Refazer e Pesquisar.
- **Entrada:** Interação do usuário via clique.
- **Processamento:** Abrir submenus ou executar rotinas correspondentes ao clicar.
- **Saída:** Menu correspondente exibido ou ação executada.

### _3.11. RF011 - Sair do Aplicativo:_

- **Descrição:** O sistema deve permitir ao usuário sair do aplicativo de forma segura.
- **Entrada:** Comando do usuário (menu, botão ou atalho de teclado).
- **Processamento:** Solicitar ao usuário para salvar mudanças não salvas.
- **Saída:** Aplicativo fechado com mudanças salvas, se desejado pelo usuário.

## **4. Requisitos Não Funcionais**

///////////////////////////////////

### _4.1. RNF001 - Desempenho_

- **Descrição:** O aplicativo deve carregar documentos de até 10 MB em menos de 2 segundos e operações de salvamento não devem demorar mais de 1 segundo em sistemas com no mínimo 4 GB de RAM e processadores equivalentes ou inferiores ao Intel Core i3.
- **Critério de Aceitação:** O desempenho deve ser verificado através de testes.

### _4.2. RNF002 - Confiabilidade_

- **Descrição:** O aplicativo deve exibir mensagens claras ao usuário em caso de falhas e deve prevenir corrupção de dados ao interromper operações incompletas, mantendo uma cópia de segurança temporária se necessário.
- **Critério de Aceitação:** O aplicativo deve exibir mensagens de erro compreensíveis e não corromper dados do usuário.

### _4.3. RNF003 - Segurança_

- **Descrição:** A aplicação deve garantir que os arquivos sejam salvos e lidos de locais seguros, verificar a integridade dos arquivos e não executar ou abrir arquivos potencialmente maliciosos.
- **Critério de Aceitação:** Implementação de verificações de segurança e sanitização de entrada.

### _4.4. RNF004 - Manutenibilidade_

- **Descrição:** O código-fonte do aplicativo deve ser modular, utilizando o padrão MVC (Model-View-Controller) do JavaFX. A documentação deve incluir comentários claros e diretrizes de uso do JavaFX para facilitar a manutenção.
- **Critério de Aceitação:**

  1. O código deve ser dividido em pacotes por responsabilidade (ex.: model, view, controller).
  2. Componentes devem reutilizar classes e métodos do JavaFX sempre que possível (ex.: FXML, SceneBuilder).
  3. Devem ser usadas ferramentas como Javadoc para documentar a API interna.

### _4.5. RNF005 - Acessibilidade_

- **Descrição:** Todos os elementos clicáveis devem possuir tooltips que expliquem suas funções ao passar o mouse.
- **Critério de Aceitação:** Testes devem confirmar que os tooltips aparecem em no máximo 1 segundo após o hover.

## 5. Riscos do Projeto

1. **Dependência de tecnologias externas:** Atualizações ou descontinuação de bibliotecas (ex.: JavaFX) podem impactar o desenvolvimento.
2. **Compatibilidade multiplataforma:** Problemas inesperados ao suportar diferentes sistemas operacionais podem exigir esforços adicionais.
3. **Desempenho:** Edição de documentos muito grandes pode afetar o tempo de resposta em sistemas com baixa capacidade de hardware.
