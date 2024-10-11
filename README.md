# prova-databigcorp

estrutura de Software para o Sistema de Vendas de Ingressos
Componentes Principais:

Frontend (Interface do Usuário):

  Tela de Login: Permite que os usuários façam login.
  Tela de Compras: Exibe a disponibilidade de ingressos em tempo real e permite que os usuários comprem ingressos.
  Feedback em Tempo Real: Notifica os usuários sobre o status de sua compra.

Backend:

API de Autenticação:

  Valida as credenciais do usuário.
  Gera e valida tokens JWT para sessões ativas.

Gerenciador de Ingressos:

  Banco de Dados: Armazena informações sobre ingressos disponíveis, usuários e transações.
  Gerenciamento de Estoque: Controla a quantidade de ingressos disponíveis e atualiza em tempo real.
  Fila de Compras: Implementa uma fila para gerenciar o acesso dos usuários ao sistema, garantindo que eles não percam a oportunidade de compra devido a latência.

Banco de Dados:

  Tabela de Ingressos: Armazena informações sobre ingressos (ID, tipo, status).
  Tabela de Usuários: Armazena informações sobre os usuários (ID, nome, email, senha hash).
  Tabela de Transações: Registra as transações de compra de ingressos.

Mecanismo de Processamento:

  Serviço de Verificação de Disponibilidade: Antes de confirmar uma compra, verifica se há ingressos disponíveis.
  Sistema de Notificação: Notifica os usuários sobre o status de suas compras e atualizações de disponibilidade.

Escalabilidade:

  Balanceador de Carga: Distribui as requisições entre várias instâncias do backend para garantir que o sistema suporte um grande número de acessos simultâneos.
  Cache: Utiliza um sistema de cache (como Redis) para armazenar informações sobre ingressos disponíveis, reduzindo a carga no banco de dados.
