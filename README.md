# Criar Máquina Virtual no Azure

## Introdução
Este item tem como objetivo descrever como criar uma máquina virtual no Azure através do portal.

## Pré-requisitos
- Ter cadastro no azure;
- Ter as permissões necessárias para poder criar máquina virtual no grupo de recursos;
- Saber para qual necessidade será utilizado a máquina para saber dimencionar os recursos, disponibilidade e escalabilidade;

## Criar uma Máquina Virtual do Azure via Portal
- Acesse o [portal do Azure](https://portal.azure.com/)
- Informe seus dados de acesso.
- No menu lateral localize e clique em `Máquinas Virtuais` conforme imagem ![Menu do Azure](/images/menu.png). Obs.: o menu pode mudar com as atualizações.
- Na próxima tela clique em `Criar` e escolha `Máquina virtual`
- Informe os dados solicitados conforme necessidade de recursos para o projeto ![detalhes de implantação](/images/detalhe.png).
- Avance para os próximos passos para configurar discos, rede, gerenciamento e monitoramento.
- No passo final revise e clique em `Criar` e aguarde ser provisionado.

# Criar Instância de Banco de dados

## Pré-requisitos
- Ter cadastro/assinatura do Azure;
- Ter as permissões necessárias para poder criar uma instância no grupo de recursos;

## Criar uma Instância do SQL do Azure via Portal

1. Acesse o [portal do Azure](https://portal.azure.com/)
2. Informe seus dados de acesso.
3. Localize `SQL do Azure` no menu lateral esquerdo, se não estiver visivel clique em `Todos os Serviços` e digite na barra de pesquisa `SQL`, então no grupo de serviços clique em `SQL do Azure`.
4. Clique em `Criar`
5. Na escolha a opção `Banco de dados SQL` e clique em `Criar` conforme ![imagem](/images/criar-instancia-sql.png).
6. Defina:
	- assinatura e grupo de recursos
	- nome para o banco de dados
	- servidor, caso não existir clique em `Criar novo` logo abaixo do campo de seleção de servidor.
	- definir o ambiente de carga de trabalho, para os testes definir `Desenvolvimento`, para implantação oficial `Produção`.
	- avalie em computação + armazenamento se está dimencionado de acordo com seu projeto, caso não estiver clique no link `Configurar banco de dados`.
	- escolha a forma de backup.
7. Clique em avançar para definir informações de rede para acesso ao banco de dados.
8. Avance para configurar detalhes de segurança.
9. Clique em `Revisar + criar`.
10. Clique em `Criar`.
11. Aguarde a implantação.
12. Você pode alterar configurações após a implantação.


