1- Verificar banco dados (hots, user, senha | depois rodar: yarn typeorm migration:run)
2- yarn install
3- yarn dev:server

obs: yarn typeorm migration:create -n nome

# Atualização do perfil

**RF**

- O usuário deve poder atualizar seu nome, email e senha;

**RNF**
 -para emails: nodemailer, ethereal, handlebars[template email]
- Utilizar Mailtrap para testar envios em ambiente de dev;
- Utilizar Amazon SES para envios em produção;
- O envio de emails deve acontecer em segundo plano (background)

**RN**

- O usuário não pode alterar seu email para um email já utilizado
- Para atualizar sua senha o usuário deve informar sua senha antiga.
- Para atualizar sua senha, o usuário precisa confirmar a nova senha;

# Recuperação de Senha

**RF**

- O usuário deve poder recuperar sua senha informando o seu e-mail.
- O usuário deve poder receber um email com instruções de recuperação de senha.
- O usuário deve poder resetar sua senha.

**RNF**

- Utilizar Mailtrap para testar envios em ambiente de dev;
- Utilizar Amazon SES para envios em produção;
- O envio de emails deve acontecer em segundo plano (background)

**RN**

- O link enviado por email para resetar a senha, deve expirar em 2h;
- O usuário precisa confirmar a nova senha ao resetar sua senha;

# Painel do Prestador

**RF**

- O usuário deve poder ver todos os agendadmentos do dia especifico
- O prestadore deve receber uma notificação sempre que houver um novo agendamento;
- O prestador deve poder visualizar as notificações não lidas;

**RNF**

- Os agendamentos do prestadores deve ser armazenada em cache;
- As notificações do prestador devem ser armazenadas no MongoDB;
- As notificações do prestador devem ser enviadas em tempo-real utilizando Socket.io

**RN**

- A notificação deve ter um status de lida ou não lida para que o prestador possa controlar;


# Agendamento de Serviço

**RF**

- O usuário deve poder listar todos prestadores de serviço cadastrados;
- O usuário deve poder listar os dias de uma mês com pelo menos um horário disponível de um prestador;
- o usuário deve poder listar horários disponíveis em um dia especifico de um prestador;
- O usuário deve poder realizar um novo agendamento com um prestador;

**RNF**

- A listagem de prestadores deve ser armazenada em cache;

**RN**

- Cada agendamento deve durar 1h exatamente;
- Os agendamentos devem estar disponíveis entre 8h às 18h (Primeiro às 8h, último às 17h)
- O usuário não pode agendar em um horário já ocupado
- O usuário não pode agendar em um horário que já passou;
- O usuário não pode agendar serviços consigo mesmo;
