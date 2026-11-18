# ÍCARO DRIVE

Aplicação demonstrativa de gestão de locações e frota, em português brasileiro.

## Publicação
O site é publicado pelo GitHub Actions / GitHub Pages a cada atualização da branch `main`.

URL prevista: https://denisguita.github.io/icarodrive/

## Funcionalidades demonstrativas
- Painel com contratos, vencimentos, valores a receber e cauções
- Cadastro de contratos e agenda de cobranças
- Registro de pagamentos parciais ou integrais
- Recibos para impressão / PDF e atalho de envio via WhatsApp
- Cadastro básico de veículos e motoristas
- Persistência local no navegador

## Aviso importante de segurança
Esta versão é um protótipo estático. Os dados ficam no armazenamento local do navegador e não são sincronizados entre dispositivos. Não cadastre CPF, CNH, endereços, contratos assinados ou comprovantes reais nesta versão. Não há autenticação, banco de dados remoto, armazenamento privado nem notificações automáticas em segundo plano.

A locadora configurada como referência é Nayane Cunha da Silva, pessoa física. A caução padrão é R$ 1.500,00, ajustável em cada contrato. A caução é tratada separadamente de receitas.

Para operação real, implementar backend com autenticação, banco de dados, controle de acesso por usuário, armazenamento privado de documentos, trilha de auditoria, rotina de lembretes no servidor e integração de assinatura eletrônica/WhatsApp. Revisar o contrato com advogado antes de usar.

Fuso horário de referência: `America/Rio_Branco`.
