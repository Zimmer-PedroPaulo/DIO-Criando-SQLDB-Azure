# DIO - Certificação AZ900 - Criando um Banco de Dados SQL na Nuvem Azure

## Escolhendo o Modelo de Serviço para o Banco de Dados no Azure (SaaS, PaaS ou IaaS)

Ao configurar um banco de dados na nuvem, uma decisão crucial é escolher o modelo de serviço que melhor se adapta às necessidades do projeto. O Azure oferece opções em SaaS, PaaS e IaaS para bancos de dados:

* **Infraestrutura como Serviço (IaaS):** Neste modelo, você tem controle total sobre a infraestrutura subjacente (servidores virtuais, armazenamento, rede). Você instala e gerencia o sistema operacional, o software do banco de dados e todas as configurações relacionadas. No Azure, isso envolveria configurar uma máquina virtual e instalar um software de banco de dados (como SQL Server, PostgreSQL ou MySQL) nela.

    * **Vantagens:** Máximo controle sobre o ambiente do banco de dados, personalização completa.
    * **Desvantagens:** Maior responsabilidade de gerenciamento, incluindo patching, backups e manutenção da infraestrutura.

* **Plataforma como Serviço (PaaS):** O provedor de nuvem (Azure) gerencia a infraestrutura e o sistema operacional, além de fornecer o software de banco de dados como um serviço. Você se concentra na configuração e no uso do banco de dados. Exemplos no Azure incluem o Azure SQL Database, Azure Database for PostgreSQL e Azure Database for MySQL (serviços gerenciados).

    * **Vantagens:** Menos responsabilidade de gerenciamento, escalabilidade facilitada, alta disponibilidade integrada, backups automáticos (geralmente).
    * **Desvantagens:** Menos controle sobre o sistema operacional e a infraestrutura subjacente, algumas opções de personalização podem ser limitadas.

* **Software como Serviço (SaaS):** O provedor de nuvem gerencia todos os aspectos do serviço, incluindo a infraestrutura, o software e os dados. O usuário final consome o serviço através de uma interface. Um exemplo no contexto de dados seria o Azure Synapse Analytics (para análise de dados em larga escala), embora não seja um banco de dados transacional tradicional. Para bancos de dados relacionais puros, a fronteira do SaaS é menos direta.

    * **Vantagens:** Mínima responsabilidade de gerenciamento, fácil de usar.
    * **Desvantagens:** Menor controle e personalização, o usuário depende totalmente das funcionalidades oferecidas pelo serviço.

## Justificativa da Escolha do Modelo

**(Aqui você deve explicar qual modelo de serviço (IaaS, PaaS ou SaaS) você escolheu para configurar sua instância de banco de dados no Azure e as razões por trás dessa decisão. Por exemplo):**

Para este desafio, optei por configurar uma instância de banco de dados utilizando o modelo **Plataforma como Serviço (PaaS)**, especificamente o **Azure SQL Database**. A escolha do PaaS se baseou nos seguintes fatores:

* **Redução da Sobrecarga de Gerenciamento:** O Azure SQL Database cuida automaticamente de tarefas como backups, patching, atualizações e alta disponibilidade, permitindo que eu me concentre na modelagem dos dados, na criação das tabelas e na interação com o banco de dados, em vez de gerenciar a infraestrutura subjacente.
* **Escalabilidade e Elasticidade:** O Azure SQL Database oferece opções de escalabilidade vertical e horizontal com poucos cliques ou através de configurações de autoescalonamento, facilitando a adaptação aos requisitos de desempenho da aplicação sem a necessidade de intervenção manual complexa na infraestrutura.
* **Custo-Benefício:** Embora o IaaS ofereça mais controle, a sobrecarga de gerenciamento e a necessidade de configurar e manter a infraestrutura podem aumentar os custos a longo prazo. O PaaS otimiza os custos ao fornecer uma plataforma gerenciada e escalável sob demanda.
* **Segurança Integrada:** O Azure SQL Database oferece recursos de segurança robustos, como criptografia, firewalls e proteção contra ameaças, gerenciados pela plataforma, o que simplifica a implementação de uma postura de segurança forte.

Embora o IaaS pudesse oferecer controle total sobre o sistema operacional e a configuração do servidor, a complexidade adicional de gerenciamento não se justifica para o objetivo deste desafio, que é praticar a configuração e o uso de um banco de dados na nuvem. O SaaS, por outro lado, embora ofereça ainda menos gerenciamento, pode não fornecer a flexibilidade necessária para configurar um banco de dados relacional tradicional da maneira que este desafio propõe.

## Modelo de Responsabilidade Compartilhada

Baseado na documentação oficial da Microsoft, a responsabilidade entre cliente e provedor varia conforme o tipo de serviço:

| Responsabilidade                            | SaaS       | PaaS         | IaaS         | No Local    |
|--------------------------------------------|------------|--------------|--------------|-------------|
| **Informações e dados**                    | Cliente    | Cliente      | Cliente      | Cliente     |
| **Dispositivos (móveis e PCs)**            | Cliente    | Cliente      | Cliente      | Cliente     |
| **Contas e identidades**                   | Cliente    | Cliente      | Cliente      | Cliente     |
| **Infraestrutura de identidade e diretório**| Compartilhada  | Compartilhada| Cliente| Cliente     |
| **Aplicativos**                            | Microsoft  | Compartilhada      | Cliente      | Cliente     |
| **Controles de rede**                      | Microsoft  | Compartilhada| Cliente      | Cliente     |
| **Sistema operacional**                    | Microsoft  | Microsoft    | Cliente      | Cliente     |
| **Hosts físicos**                          | Microsoft  | Microsoft    | Microsoft    | Cliente     |
| **Rede física**                            | Microsoft  | Microsoft    | Microsoft    | Cliente     |
| **Datacenter físico**                      | Microsoft  | Microsoft    | Microsoft    | Cliente     |

---

## Passos para Configurar a Instância de Banco de Dados (Modelo PaaS - Azure SQL Database)

1.  Acessar o portal do Azure ([https://portal.azure.com/](https://portal.azure.com/)).
2.  Criar um novo Grupo de Recursos.
3.  Pesquisar e selecionar o serviço "Bancos de dados SQL".
4.  Clicar em "Criar banco de dados SQL" e preencher as informações necessárias (nome do banco de dados, servidor, etc.).
5.  Configurar o servidor SQL (criar um novo ou usar um existente).
6.  Definir a configuração de computação e armazenamento.
7.  Configurar as regras de firewall para permitir o acesso.
8.  Configurar a autenticação.
9.  Revisar e criar o banco de dados.
10. Conectar-se ao banco de dados utilizando ferramentas como o SQL Server Management Studio.
