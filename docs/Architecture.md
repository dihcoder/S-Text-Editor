# Technical Architecture Design Document

## Aplicação S Text Editor

### 1. Visão geral do sistema

O S Text Editor é um aplicativo de desktop em Java que fornece recursos básicos de edição de texto, gerenciamento de arquivos e uma interface amigável. O aplicativo segue o padrão arquitetônico Model-View-Controller (MVC) para garantir a divisão de responsabilidades e a manutenibilidade.

### 2. Padrão de Arquitetura

#### Model-View-Controller (MVC)

- **Model**: Gerencia o conteúdo do texto, operações de arquivo e estado da aplicação.
- **View**: Manipula os elementos da interface do usuário e os exibe usando JavaFX FXML.
- **Controller**: Processa as entradas do usuário e gerencia a comunicação entre o Model e o View.

#### Componentes Principais

```
com.stexteditor/
├── model/
│   ├── Document.java          # Representa o documento de texto e seu conteúdo
│   ├── FileManager.java       # Lida com operações de arquivo (leitura/gravação)
│   └── TextBuffer.java        # Gerencia o conteúdo de texto e as operações de edição
├── view/
│   ├── fxml/
│   │   ├── main.fxml           # Layout da janela principal
│   │   ├── menubar.fxml        # Layout do da barra de menu
│   │   └── dialogs.fxml        # Layout de caixas de diálogo
│   ├── MainWindow.java         # Controlador da janela principal da aplicação
│   ├── MenuBarController.java  # Controlador da barra de menu
│   └── StatusBar.java          # Controlador da barra de status
├── controller/
│   ├── MainController.java     # Controlador principal da aplicação
│   ├── FileController.java     # Controlador de operações de arquivo
│   └── EditController.java     # Controlador de operação de edição de texto
└── util/
    ├── Config.java             # Configuração do aplicativo
    └── Logger.java             # Registro do aplicativo
```

### 3. Principais decisões técnicas

#### Framework de UI

- **JavaFX**: Escolhido por seus recursos modernos, conjunto de componentes de interface e suporte a estilização com CSS
- FXML para o desenho de layouts de interface
- Estilização CSS para customização de aparência

#### Processamento de texto

- TextArea do JavaFX para edição básica de texto
- Suporte para operações de desfazer/refazer usando os métodos built-in do JavaFX
- Manipulação de arquivos grandes com eficiência de memória por meio de leitura/escrita em buffer

### 4. Requisitos técnicos

#### Requisitos de desempenho

- Carregamento de arquivo: < 2 segundos para arquivos de até 10 MB
- Responsividade da IU: < 50 ms para operações básicas
- Uso de memória: < 100 MB para operação normal

#### Requisitos de segurança

- Acesso ao arquivo limitado às permissões do usuário
- Backup automático de alterações não salvas
- Manipulação segura de arquivos temporários

### 5. Tratamento de erros

- Tratamento abrangente de exceções para operações de arquivo
- Caixas de diálogo de alerta JavaFX para mensagens de erro amigáveis
- Recuperação automática de travamentos
- Registro de erros para depuração

### 6. Estratégia de teste

#### Teste de unidade

- JUnit 5 para teste de componentes
- TestFX para teste de IU em JavaFX
- Mock Objects para dependências externas
- Meta de cobertura de teste: 80%

#### Teste de integração

- Teste de ponta a ponta dos principais fluxos de trabalho
- Teste de automação de IU com TestFX
- Teste de desempenho para arquivos grandes

### 7. Dependências externas

- Java SE Development Kit 17+
- JavaFX SDK 17+
- JUnit 5.x para teste
- TestFX para teste de IU
- Log4j para registro
- Apache Commons IO para operações de arquivo

### 8. Diretrizes de desenvolvimento

- Convenções de nomenclatura e organização FXML
- Guia de estilos CSS
- Controle de versão: Git com fluxo de trabalho baseado em feature branch
- Revisão de código necessária para todas as alterações
