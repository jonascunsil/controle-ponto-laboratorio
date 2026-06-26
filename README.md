# Controle de Ponto — Laboratório

Sistema simples de controle de presença para laboratórios. O aluno registra entrada e saída digitando o CPF num computador na entrada, e o responsável acompanha o total de horas por aluno, com exportação para Excel.

Funciona inteiramente no navegador (Chrome ou Edge), em um único arquivo HTML, sem instalação e sem mensalidade.

## Para que serve

Laboratórios acadêmicos costumam precisar controlar as horas dos alunos, mas os softwares de ponto do mercado são voltados para registro de jornada CLT: caros e cheios de funções desnecessárias para esse caso. Este projeto resolve apenas o que o laboratório precisa, de forma direta.

## Como funciona

- Um computador fica na entrada do laboratório, em tela cheia (modo quiosque).
- O aluno digita o CPF (no teclado da tela ou no teclado físico) e confirma.
- O sistema detecta automaticamente se é **entrada** ou **saída** e mostra uma confirmação na tela.
- O responsável acessa a área de administração (protegida por PIN) para ver o total de horas por aluno, consultar todos os registros e exportar os dados.

## Funcionalidades

- Registro de entrada e saída por CPF, com detecção automática.
- Validação dos dígitos do CPF (pode ser desativada nas configurações).
- Contador de quantas pessoas estão no laboratório no momento.
- Cadastro de alunos restrito ao administrador, evitando duplicatas por erro de digitação.
- Relatório de horas por aluno, com filtro por período.
- Histórico completo de entradas e saídas, com correção de registros.
- Encerramento de entradas em aberto (para quando alguém esquece de registrar a saída).
- Exportação para CSV (abre direto no Excel, com acentuação correta).
- Dados salvos localmente, com opção de gravar num arquivo sincronizado pelo Google Drive.

## Como usar

1. Baixe o arquivo `index.html`.
2. Abra no Chrome ou Edge (dois cliques).
3. Pressione **F11** para deixar em tela cheia.
4. Entre na **Administração** (botão no rodapé) com o PIN padrão **1234** e:
   - troque o PIN nas Configurações;
   - defina o nome do laboratório;
   - cadastre os alunos na aba **Alunos**.
5. Pronto. A partir daí, os alunos já podem registrar o ponto.

## Backup e Google Drive (opcional)

Por padrão, os dados ficam salvos apenas no navegador daquele computador. Para ter backup e acesso na nuvem:

1. Instale o **Google Drive para computador** no PC do laboratório.
2. Na aba **Configurações**, clique em **Conectar/criar arquivo** e salve o `ponto-dados.json` dentro da pasta do Google Drive.

A partir daí, cada registro é gravado nesse arquivo automaticamente, e o Drive sincroniza para a nuvem. Recomenda-se exportar uma cópia (CSV ou JSON) periodicamente como segurança.

## Privacidade (LGPD)

O sistema lida com dados pessoais (nome e CPF dos alunos). Por isso:

- **Nunca** publique o arquivo `ponto-dados.json` em local público (como este repositório). Somente o programa (`index.html`) deve ficar público.
- Troque o PIN padrão antes de usar.
- Use os dados apenas para a finalidade de controle de presença.

## Tecnologia

HTML, CSS e JavaScript, em um único arquivo, sem dependências externas. Os dados são armazenados no navegador (localStorage) e, opcionalmente, em um arquivo local via File System Access API.

## Licença

Uso livre. Adapte conforme a necessidade do seu laboratório.
