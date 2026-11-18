# Configurar o acesso privado da ÍCARO DRIVE

O login da aplicação usa Supabase Auth. A interface fica bloqueada até existir uma sessão válida para o e-mail autorizado.

## 1. Criar projeto Supabase
1. Crie um projeto no Supabase.
2. Em Project Settings > API, copie Project URL e a chave publishable/anon.
3. Edite `auth-config.js` no GitHub e substitua os dois valores de exemplo.
4. Nunca use a chave `service_role` no navegador ou neste repositório.

## 2. Criar a única conta autorizada
1. No Supabase, abra Authentication > Users.
2. Crie/invite manualmente o usuário `denisguita@yahoo.com.br`.
3. Defina uma senha forte e exclusiva diretamente no painel seguro do Supabase.
4. Desative o cadastro público (Authentication > Providers > Email > Allow new users / Enable signups, conforme a versão do painel).
5. A interface só aceita o e-mail autorizado. Não existe botão de cadastro.

Não reutilize senha curta ou senha que tenha sido compartilhada em conversa. Use pelo menos 12 caracteres, com letras, números e símbolos.

## 3. Habilitar redefinição por e-mail
1. Configure SMTP próprio em Authentication > SMTP Settings. O SMTP padrão de teste do Supabase tem limites e não é adequado para produção.
2. Em Authentication > URL Configuration, adicione o endereço público do GitHub Pages à Site URL e Redirect URLs, por exemplo:
   `https://denisguita.github.io/icarodrive/`
3. Personalize o template de recuperação de senha.
4. Teste Esqueci minha senha e confirme que o link retorna para o site.

## 4. Limites importantes desta versão
- O login protege a interface por Supabase Auth.
- Os registros operacionais ainda ficam no localStorage deste navegador; eles não estão sincronizados entre dispositivos nem protegidos por políticas de banco de dados.
- Antes de inserir CPF, CNH, endereço, contratos ou outros dados reais, migrar os registros para tabelas Supabase com Row Level Security (RLS), políticas restritas ao usuário autorizado e armazenamento privado.
- GitHub Pages publica arquivos estáticos. Não coloque segredos, senhas, tokens administrativos ou service_role no repositório.
