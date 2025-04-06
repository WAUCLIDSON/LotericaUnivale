# Lotérica-Univale
PORTFÓLIO DO SISTEMA DE ATENDIMENTO – CASA LOTÉRICA / UNIVALE
==============================================================

1. VISÃO GERAL
--------------
O sistema “Casa Lotérica / Univale” é uma aplicação de console desenvolvida em C# para gerenciar o atendimento em uma casa lotérica.
Ele possui duas áreas principais:
• Área do Cliente: Permite que o cliente retire sua senha para atendimento, escolha o tipo de serviço (pagar, receber, jogos ou preferencial) e, opcionalmente, indique se deseja ser atendido por um atendente específico.
• Área Administrativa: Protegida por senha, onde o gerente pode chamar a próxima senha, visualizar relatórios de atendimentos, conferir o desempenho de cada caixa e gerar um relatório completo em formato TXT.

2. FUNCIONALIDADES
------------------
Área do Cliente:
- Escolha do Serviço: Seleção entre “Pagar”, “Receber”, “Jogos” e “Preferencial”.
- Entrada de Valor: O cliente informa o valor associado ao atendimento.
- Preferência de Atendente: O cliente pode optar por ser atendido por um atendente específico (Wauclidson, Vitor, Henrique ou Anderson).
- Geração de Senha: Uma senha única é gerada e informada ao cliente, que deverá aguardar ser chamado.

Área Administrativa:
- Chamada da Próxima Senha: O gerente chama o próximo atendimento, priorizando a fila preferencial e, se necessário, definindo o caixa (e atendente) a ser utilizado.
- Relatório de Atendimentos: Lista todos os atendimentos realizados com detalhes (senha, tipo, valor, atendente).
- Relatório de Encaminhamento de Caixa: Exibe o total de atendimentos e o valor acumulado para cada caixa.
- Fechamento Total da Lotérica: Apresenta o total de atendimentos e valores gerais e permite a geração de um relatório em arquivo TXT.

Interface Visual:
- Cabeçalho Padronizado: Cada tela exibe um cabeçalho com cores e mensagens padronizadas.
- Logo: Ao final de cada tela, o logo "v&w/soluções" é exibido, reforçando a identidade visual do sistema.

3. ESTRUTURA DO CÓDIGO
----------------------
• O código está organizado em um namespace “Caixa” com a classe principal “Programa”.
• Existem duas estruturas principais:
   - Documento: Representa dados do cliente (não utilizada diretamente no fluxo principal).
   - SenhaCli: Representa o ticket de atendimento, com atributos para o número da senha, tipo de serviço, valor, preferência de atendente e o atendente que realizou o atendimento.
• Foram utilizadas estruturas de dados:
   - Queue: Para gerenciar a fila de atendimentos (normal e preferencial).
   - Stack: Para cada caixa (cada atendente possui uma pilha de atendimentos realizados).
   - List: Para registrar todos os atendimentos e gerar relatórios.

Principais métodos:
- MostrarCabecalho() e MostrarLogo(): Garantem a consistência visual do sistema.
- MenuNovaSenha() & NovaSenha(): Gerenciam a retirada de senha e a opção de atendimento por um atendente específico.
- AreaAdministrativa(): Protegida por senha, apresenta um submenu para chamar a próxima senha, gerar relatórios e fechar a lotérica.
- NovoAtendimento(): Chama a próxima senha, priorizando a fila preferencial e solicitando a escolha do caixa, se necessário.
- RelatorioAtendimentos(), RelatorioEncaminhamentoCaixa() e FechamentoTotalLoterica(): Geram relatórios detalhados dos atendimentos e possibilitam a exportação dos dados para TXT.

4. TECNOLOGIAS UTILIZADAS
-------------------------
- Linguagem: C#
- Plataforma: .NET (aplicação console)
- Estruturas de Dados: Queue, Stack, List
- Manipulação de Arquivos: StreamWriter para exportação de relatórios em formato TXT

5. RESUMO E PRÓXIMAS MELHORIAS
------------------------------
Facilidades do Código:
• Estruturação clara e modular, com métodos bem definidos que facilitam a manutenção e escalabilidade.
• Uso eficiente de estruturas de dados (Queue, Stack, List) para gerenciar o fluxo de atendimentos.
• Interface de console consistente com cabeçalho e logo padronizados, reforçando a identidade visual.
• Flexibilidade, permitindo que o cliente escolha um atendente específico e possibilitando relatórios gerenciais detalhados.

Possíveis Melhorias Futuras:
1. Persistência de Dados: Integrar um banco de dados (SQL Server, SQLite) para salvar os atendimentos e permitir consultas históricas.
2. Interface Gráfica: Migrar de console para uma interface gráfica (usando Windows Forms ou WPF) para uma experiência mais intuitiva.
3. Aplicação de Padrões de Projeto: Utilizar padrões como Observer, Factory e seguir os princípios SOLID para melhorar a organização e manutenção do código.
4. Validação e Tratamento de Erros: Implementar validações mais robustas e tratamento de exceções para aumentar a confiabilidade do sistema.
5. Sistema de Logging: Adicionar um sistema de log (com NLog ou log4net) para facilitar o monitoramento e a depuração do sistema.

Referências:
- "C# in a Nutshell" (Joseph Albahari & Ben Albahari)
- "CLR via C#" (Jeffrey Richter)
- "Design Patterns: Elements of Reusable Object-Oriented Software" (Erich Gamma et al.)

6. CONSIDERAÇÕES FINAIS
------------------------
O sistema "Casa Lotérica / Univale" foi desenvolvido para oferecer uma solução robusta e flexível para o gerenciamento de atendimentos. Com uma interface simples e relatórios gerenciais, o sistema atende tanto aos clientes quanto aos gerentes. As melhorias futuras visam aumentar a escalabilidade, a experiência do usuário e a confiabilidade do sistema.

v&w/soluções
