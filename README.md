# Criar Máquina Virtual no Azure

## Introdução
Este item tem como objetivo descrever como criar uma máquina virtual no Azure através do portal.

## Pré-requisitos
- Ter cadastro no azure;
- Ter as permissões necessárias para poder criar máquina virtual no grupo de recursos;
- Saber para qual necessidade será utilizado a máquina para saber dimencionar os recursos, disponibilidade e escalabilidade;

## Criar uma Máquina Virtual do Azure via Portal
- Acesse o [portal do Azure](https://portal.azure.com/);
- Informe seus dados de acesso;
- No menu lateral localize e clique em `Máquinas Virtuais` conforme imagem [Menu do Azure](/images/menu.png). Obs.: o menu pode mudar com as atualizações;
- Na próxima tela clique em `Criar` e escolha `Máquina virtual`;
- Informe os dados solicitados conforme necessidade de recursos para o projeto [detalhes de implantação](/images/detalhe.png);
- Avance para os próximos passos para configurar discos, rede, gerenciamento e monitoramento;
- No passo final revise e clique em `Criar` e aguarde ser provisionado;

# Criar Instância de Banco de dados

## Pré-requisitos
- Ter cadastro/assinatura do Azure;
- Ter as permissões necessárias para poder criar uma instância no grupo de recursos;

## Criar uma Instância do SQL do Azure via Portal

1. Acesse o [portal do Azure](https://portal.azure.com/);
2. Informe seus dados de acesso;
3. Localize `SQL do Azure` no menu lateral esquerdo, se não estiver visivel clique em `Todos os Serviços` e digite na barra de pesquisa `SQL`, então no grupo de serviços clique em `SQL do Azure`;
4. Clique em `Criar`;
5. Na escolha a opção `Banco de dados SQL` e clique em `Criar` conforme [imagem](/images/criar-instancia-sql.png);
6. Defina:
	- assinatura e grupo de recursos;
	- nome para o banco de dados;
	- servidor, caso não existir clique em `Criar novo` logo abaixo do campo de seleção de servidor;
	- definir o ambiente de carga de trabalho, para os testes definir `Desenvolvimento`, para implantação oficial `Produção`;
	- avalie em computação + armazenamento se está dimencionado de acordo com seu projeto, caso não estiver clique no link `Configurar banco de dados`;
	- escolha a forma de backup;
7. Clique em avançar para definir informações de rede para acesso ao banco de dados;
8. Avance para configurar detalhes de segurança;
9. Clique em `Revisar + criar`;
10. Clique em `Criar`;
11. Aguarde a implantação;
12. Você pode alterar configurações após a implantação;

# Construindo Arquitetura no Azure

- Acessar o [site](https://azure.microsoft.com/pt-br/explore/global-infrastructure) para informações oficiais referente a infraestrutura do azure;
- A microsoft disponibiliza acesso a um globo virtual através do [site](https://datacenters.microsoft.com/globe/explore). Através do globo é possível:
	- Visualizar geograficamente onde estão localizado os datacenters e como se comunicam;
	- Clicando nos pontos que estão no globo apresenta informações detalhadas como:
		- Localização;
		- Onde fica o datacenter de replicação;
		- Quantas zonas tem disponível;
		- Ano de abertura;
		- Residência dos dados, importante em caso de informações sensiveis que não podem sair do país;
		- Dentre outras informações importantes para tomas de decisão no momento de montar a infraestrutura no Azure;

## Criando Recursos no Portal

1. Acesse o [portal do Azure](https://portal.azure.com/);
2. Informe seus dados de acesso;
3. Localize a opção `Grupos de Recursos`;
4. Clique em `Criar`;
5. Selecione a assinatura caso tenha mais de uma;
6. Informe o nome;
7. Opcionalmente pode adicionar marcações no recurso, exemplo, informar um centro de custo para facilitar no momento da fatura;
8. Revisar e Criar, clique em `Criar`;

Após criado o grupo de recurso pode ser concedido acesso através da opção `IAM (Controle de acesso)`, isso dará acesso a tudo que tiver vinculado ao grupo de recurso.
Pode ser criado bloqueios para evitar por exemplo exclusão de recursos.

# Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure

1. Acesse o [portal do Azure](https://portal.azure.com/);
2. Informe seus dados de acesso;
3. Localize a opção `Máquinas Virtuais`;
4. Clique em `Criar`;
5. Escolha uma das opções:
	- Tem opções já pre-definidas com recursos dimencionados;
6. Para definir todas as informações clique na primeira opção:
	- Definir assinatura;
	- Grupo de recursos;
	- Nome;
	- Região;
	- Opção de disponibilidade, conjunto de dimencionamento para dias de pico, exemplo black friday;
	- Zona de disponibilidade;
	- Tipo de segurança;
	- Imagem (Sistema Operacional)
	- Tamanho da máquina (vcpu, memória);
	- Nome de usuário e senha;
	- Porta de entrada;
	- Avançar para definir:
		- Discos;
		- Rede;
		- Gerenciamento;
		- Monitoramento;
		- Marcas;
	- Revisar e Criar;
	
# Dominando o Armazenamento na Azure

O Azure disponiviliza armazenamento em arquivos podendo ser mapeado como unidade de rede para compartilhamento, Blob, tabelas (chave/valor) e fila de mensagens.
Pode ser armazenado todo tipo de arquivo. Para o Blob pode escolher qual nivel de acesso que terá o arquivo no futuro e com base nisso varia o preço.

Para criar uma conta deve-se selecionar a assinatura, o grupo de recursos, definir o nome, o nome deve ser unico mundialmente, pois através desse nome será montado o endereço para acessar os arquivos, blobs, ETC..
Definir desempenho e qual modelo de redundância.

Após criado a conta é possivel gerenciar os recursos para armazenamento de arquivo, blob, filas e tabelas.

Para migração de grandes volumes é disponibilizado a opção de usar um hardware chamado Data Box onde é levado até o cliente copiado os dados e depois levado até um data center do Azure para agilizar a migração.
Tem ferramentas para auxiliar a migração de servidores, banco de dados e aplicativos web.

# Entendendo sobre Segurança e Identidade na Azure

Para quem já tem um ambiente com usuários pode sincronizar com o Entra ID, serviço responsável por concentrar e gerenciar as contas de usuários.
Não tem sincronização da nuvem com o ambiente on primese, então se criar um usuário na nuvem e não vai sincronizar.
No Entra ID pode ser definico os usuários, grupos, regras e várias outras definições.
Concentra um log de todos os acessos dos usuários contendo origem e IP.
Por segurançã ao excluir um usuário ele permanece disponível para restaurar por 30 dias, porém não consegue mais logar. É apenas para caso necessite restaurar o usuário.
Pode criar usuário pelo próprio portal um a um ou importar um CSV para enviar convite para diversos usuários.
O serviço tem um SLA de 99,99%.
Tendo o usuário cadastrado pode dar permissão aos recursos do azure, este permissionamento é herdavel, ou seja, se der acesso ao grupo de recurso o usuário terá acesso a todos os recursos que tiverem vinculado. Assim como pode entrar em cada recurso é dar permissão somente a ele. 

O Microsoft Defender for Cloud tem toda parte de recomendação de segurança com alertas de vulnerabilidades.
Tem o módulo DevOps Security permitindo conectar contas como do github para monitoramento. Também permite monitorar contas de outras clouds como AWS e GCP, tendo tudo em um único painel.

# Otimizando Custos no Azure

O Azure disponibiliza uma calculadora para poder ter uma estimativa do custo que terá ao migrar ou começar a usar o Azure. Está disponível no endereço (https://azure.microsoft.com/pt-br/pricing/calculator/)[https://azure.microsoft.com/pt-br/pricing/calculator/]
Na calculadora pode definir todos os recursos que serão necessários como VMs, banco de dados, discos, rede, licenças dentre outros, definir localização geográfica que será alocado os recursos e com base nessas informações sera apresentado um valor estimado.
Ao final da simulação é possível exportar um relatório para passar para outras pessoas avaliarem.
