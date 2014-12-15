Projeto Biblioteca
=================
Plano de Gerenciamento de Configuração
======================================
Versão 1.5
------------------

Histórico de Versões
--------------------

|Data                |Versão       |Descrição               |Autor          |
|--------------------|-------------|------------------------|---------------|
|13/12/2014 | 1.0 | Versão inicial. | Thaís de Almeida |
|14/12/2014 | 1.1 | Inclusão de Seção 4. | Thaís de Almeida |
|14/12/2014 | 1.2 | Inclusão de Seção 1.3, 3.1.3 e 6 | André Rocha |
|14/12/2014 | 1.3 | Inclusão de Seção 1.1, 3.2.2 e 5 | Manoela Freitas |
|15/12/2014 | 1.4 | Inclusão de Seção 1.2, 1.5, 2.1 e 3.1.4 | Fernando Freitas |
|15/12/2014 | 1.5 | Inclusão de Seção 2.2.1, 2.2.2, 3.1.1 e 3.1.2 | Emanuela Mascarenhas |



1. Introdução
==============

1.1 Finalidade
---------------
Este documento tem o objetivo de descrever o plano de Gestão de Configuração e Mudança para o estabelecimento da configuração do projeto Biblioteca.

1.2 Escopo
----------
Este documento é destinado a todos os integrantes da equipe responsável pelo projeto Biblioteca e abrange todo o controle e gerenciamento da configuração do projeto, tais como requisitos, casos de uso, diagramas, arquivos de código-fonte, modelos de dados, casos de teste e manuais.

1.3 Definições, Acrônimos e Abreviações
---------------------------------------
 NOMN - Nome do projeto, acronimo utilizado no inicio do nome de todos os artefatos.<br>
 Jira - Ferramenta da Atlassian para controle de mudanças.<br>
 SVN  - Subversion - Ferramenta open source de controle de configuração de software.

1.4 Referências
---------------

Não se aplica.

1.5 Visão Geral
---------------
As próximas seções deste documento estão divididas conforme descrito abaixo:

A seção 2 descreve os papéis e suas responsabilidades das atividades,  ferramentas utilizadas e os procedimentos necessários para realização do controle de versão dos itens de configuração gerados no ciclo de vida do projeto.

A seção 3 descreve como os itens de configuração devem ser identificados, as Baselines do projeto,a estrutura do repositório e a organização dos itens dentro do repositório.

A seção 4 são abordados os padrões e procedimentos que devem ser seguidos no projeto.

A seção 5 descreve as ferramentas de software, o pessoal e o treinamento necessários para implementar as atividades de CM especificadas.

A seção 6 descreve o cronograma das auditorias de configuração e o que será verificado. Também informa como serão reportados os problemas encontrados e como será feito o acompanhamento das correções.


2. Gerenciamento de Configuração de Software
============================================

2.1 Organização, Responsabilidades e Interfaces
------------------------------------------------

| Papéis	                      | Equipe		  	      | Responsabilidade     |
|----------------------------------------|-----------------------------|---------------------------|
|Gerente de Configuração|Thaís de Almeida|Estabelecer Políticas de GC <br> Escrever Plano de GC <br> Configurar Ambiente de GC <br> Criar Espaços de Trabalho de Integração <br> Criar Baselines <br> Promover Baselines|
|CCM|Manoela Freitas, <br> Emanuela Mascarenhas|Estabelecer Processo de Controle de Mudanças <br> Revisar Solicitação de Mudança <br> Aprovar ou rejeitar solicitações de mudanças|
|Desenvolvedor|Fernando Italo, <br> Andre Rocha|Seguir os padrões e procedimentos definidos no plano de gerência de configuração|

2.2 Ferramentas, Ambiente e Infra-estrutura
-------------------------------------------
### 2.2.1 Ferramentas
| Nome	                      | Descrição		  	      | Versão     | Licença     |
|----------------------------------------|-----------------------------|---------------------------|---------------------------|
|Git|Controle de versão distribuído|2.2.0|Free|
|GitHub|Serviço de hospedagem de repositório Git (privado)|...|$ 7,00 / mês|
|Jira|Ferramenta de controle de mudanças|6.1.4|$ 10,00 / mês|
|MySQL|Servidor de Banco de Dados|5.6|Free|
|MySQL Workbench|Client MySQL|6.2|Free|
|PHPStorm|IDE para desenvolvimento PHP|8|$ 199,00 /ano|
|Ubuntu|Sistema Operacional|14.0|Free|
|Xampp|Ambiente de Desenvolvimento PHP|5.6.3|Free|
|PHP|Linguagem de programação web|5.5|Free|
|Apache|Servidor de aplicações web|2.4.7|Free|

### 2.2.2 Ambiente e Infra-estrutura
### Banco de Dados
O banco de dados utilizado no projeto é PostgresSQL. Serão definidos três bancos de dados: Desenvolvimento, Homologação e Produção. Banco de Desenvolvimento é o banco utilizado pelos desenvovledores nas atividades de desenvolvimento ou testes. Banco de Homologação é o banco utilizado pelas versões do sistema a serem homologadas pelo cliente. Banco de Produção é o banco utilizado pelas versões definitivas disponibilizadas ao cliente. Os bancos de dados estarão configurados da seguinte maneira:

| Banco de Desenvolvimento	                             |      		  	         | 
|-------------------------------------------------------|--------------------|
|IP|192.168.1.1|
|Porta|3306|
|Nome do banco|bibliotecabd_dev|
|Sistema Operacional|Ubuntu|
|Hardware|Intel® Core™ i5-4210H Processor (3M Cache, up to 3.50 GHz)	3.0 MB	2.90 GHz, 4GB RAM, 500 HD|

| Banco de Homologação	                      | 		  	              | 
|--------------------------------------------|--------------------|
|IP|192.168.1.2|
|Porta|3306|
|Nome do banco|bibliotecabd_homolog|
|Sistema Operacional|Ubuntu|
|Hardware|Intel® Core™ i5-4210H Processor (3M Cache, up to 3.50 GHz)	3.0 MB	2.90 GHz, 4GB RAM, 500 HD|

| Banco de Produção	                      | 		  	             | 
|-----------------------------------------|-------------------|
|IP|192.168.1.7|
|Porta|5432|
|Nome do banco|Bibliotecabd|
|Sistema Operacional|Ubuntu|
|Hardware|Intel® Core™ i7-4980HQ Processor (6M Cache, up to 4.00 GHz)	6.0 MB	2.80 GHz, 8GB RAM, 1TB HD|

### Controle de Versão
A ferramenta de controle de versão utilizada no projeto será o GIT, uma ferramenta de controle de versão distribuído. Também será usado o serviço GitHub para hospedar o repositório remoto do projeto. Este repositório deverá ser privado. O custo com o serviço de hospedagem do repositório é de $7.00 por mês. Os desenvolvedores da equipe deverão criar um repositório local que deverá ser um "clone" do repositório remoto em sua estação de desenvolvimento.

| Repositório Remoto	                      |         		  	      |
|----------------------------------------|-----------------------------|
|Endereço|https://github.com/biblioteca/projetobiblioteca|

### Controle de Mudanças
Para controle de mudanças, será utilizado no projeto a ferramenta Jira. Todos os membros da equipe do projeto deverão ter um usuário para acesso, assim como os clientes que irão solicitar as mudanças.

| Servidor Jira	                      |         		  	      |
|----------------------------------------|-----------------------------|
|IP|192.168.1.8|
|Porta|8080|
|Endereço|http://102.168.1.8:8080/secure/Dashboard.jspa|
|Sistema Operacional|Linux Debian|
|Hardware|Processador Intel® Core i5 2.8 GHz, 4GB RAM, 500 HD|

### Servidores de Aplicação
O servidor de aplicação utilizado pelo projeto será o JBoss. Serão disponiblizados dois servidores de aplicação, Homologação, no qual serão implantadas as versões a serem homologadas pelo cliente, e Produção, onde serão implantadas as versões finais a serem disponibilizadas ao cliente. Os desenvolvedores também terão um servidor JBoss rodando localmente em suas estações de desenvolvimento.

| Servidor JBoss de Homologação	                      |         		  	      |
|----------------------------------------|-----------------------------|
|IP|192.168.1.9|
|Porta|8080|
|Sistema Operacional|Linux Debian|
|Hardware|Processador Intel® Core i5 2.8 GHz, 4GB RAM, 500 HD|

| Servidor JBoss de Produção	                      |         		  	      |
|----------------------------------------|-----------------------------|
|IP|192.168.1.10|
|Porta|8080|
|Sistema Operacional|Linux Debian|
|Hardware|Processador Intel® Xeon® Quad-Core 3.10GHz, 8GB RAM, 500 HD|

### Configuração da Área de Trabalho
A edição de código-fonte será feita através da IDE Eclipse. A documentação do projeto deverá ser feita utilizando a ferramenta LibreOffice salvando no formato ODF (Open Document Format). As estações de trabalho de desenvolvimento deverão ter as seguintes configurações:

| Área de Trabalho	                      |         		  	      |
|----------------------------------------|-----------------------------|
|Sistema Operacional|Linux Ubuntu|
|Hardware|Processador Intel® Core i7 3.4GHz, 8GB RAM, 500 HD|
|Softwares|Git, Eclipse + EGit, pgAdmin, Java JDK, JBoss, Libre Office|

3. O Programa de Gerenciamento de Configuração
==============================================

3.1 Identificação da Configuração
---------------------------------
### 3.1.1 Métodos de Identificação

Os itens de configuração devem possuir um identificador único. A identificação para os itens de processo segue o formato abaixo:

(NOME_DO_PROJETO)_(NOME_ DO_ARTEFATO)_(VERSÃO).EXTENSÃO

Ex: Biblioteca_Cronograma_v1.mpp
	       	
Para os itens de código cada classe deve seguir a identificação abaixo:

(NOME_ DA_CLASSE).EXTENSÃO

Ex: Login.php

### 3.1.2 Itens de Configuração
Os itens de configuração do processo de desenvolvimento de software são os artefatos que estão sob a gerência de configuração. Alguns documentos produzidos pelo projeto Biblioteca não serão tratados como itens de configuração, embora mantenhamos estes documentos no repositório. Trataremos como itens de configuração do processo de software os seguintes itens:

| Item (ou Tipo de Item)                 | Responsável na equipe	     | Inclusão em Baseline |
|----------------------------------------|-----------------------------|----------------------|
|Documento de Requisitos|Analista de requisitos|Modificação ou remoção de requisito existente <br> Criação de novo requisito|
|Documento de Teste|Analista de teste|Execução de testes funcionais|
|Manual do usuário|Desenvolvedor: Andre Rocha|Desenvolvimento de nova funcionalidade|
|Código fonte|Desenvolvedor: Fernando Freitas|  -  |
|Plano de Projeto de Software|Gerente do Projeto: Emanuela Mascarenhas|Alteração em itens do Plano|
|Planilha de acompanhamento de mudanças|CCB: Manoela Freitas|Adição de nova mudança <br> Alteração de status da mudança|
|Cronograma|Gerente do Projeto: Emanuela Mascarenhas|Modificação de prazos <br> Alteração/remoção/adição de atividades|

### 3.1.3 Baselines do Projeto

| Tipo da Baseline	                      | Label da Baseline		  	      | Data/Marco de criação     |  Conteúdo              |
|----------------------------------------|-----------------------------|---------------------------|------------------------|
|Requisitos|xpto_nomn_01_requisitos_01|Definido no Jira|01/10/2012|NOMN_ECU_caso_de_uso_01|
|Teste|xpto_nomn_01_testes_01|Definido no Jira|20/10/2012|NOMN_ECU_caso_de_uso_01, Plano de teste do caso de uso|
|Release|xpto_nomn_01_release_01|Definido no Jira|01/11/2012|Código fonte, release notes, relatório de testes|

### 3.1.4 Estrutura do Repositório de Versões

Os projetos deverão seguir a seguinte estrutura de pastas no repositório:

_Exemplo:_ **SIGLA DO CLIENTE\>SIGLA DO PROJETO\>DIRETÓRIO\>SUBDIRETÓRIO\(ARTEFATOS\)**

| Diretório | Subdiretório | Artefatos |
|-----------|--------------|-----------|
| Documentos | Gerência de Configuração | Modelo do Plano de Gerenciamento de configuração <br> Relatório de Acompanhamento de Projeto <br> Notas de Releases e Arquivos de aprovação dos documentos. |
| Documentos | Gerência de Projetos | Documento de Visão <br> Termo de Abertura <br> Plano de Projeto <br> Cronograma <br> Relatório de Status <br> Atas de Reuniões <br> Arquivos de aprovação dos documentos. |
| Documentos | Requisitos | Especificação de Caso de Uso <br> Modelo de Caso de Uso <br> Glossário e Arquivos de aprovação dos documentos. |
| Documentos | Analise e Projeto | Manual de Implantação <br> Documento de Arquitetura <br> Modelo de Banco de Dados <br> Modelo de Análise e Projetos <br> Arquivos de aprovação dos documentos. |
| Documentos | Gerência de Mudança | Planilha de Acompanhamento de Mudanças <br> Formulário de Solicitação de Mudança <br> Relatório de Controle de Mudança <br> Arquivos de aprovação dos documentos |
| Aplicação | ... | Códigos Fonte |

Caso exista algum projeto onde a estrutura de pastas não atenda, será gerada uma adaptação e esta deverá ser descrita no _Plano de Projeto_.

A responsabilidade de operacionalizar esses procedimentos ficará a cargo do _Analista de Gestão de Configuração_.

3.2 Controle de Configuração e Mudança
--------------------------------------

### 3.2.1 Processamento e Aprovação de Solicitações de Mudança
Seguindo os valores ágeis, mudanças são bem-vindas e aceitas até mesmo em um estado tardio do projeto. Logo, para que isso seja alcançado, o processo de mudanças deve ser simples. 

Assim que uma mudança é solicitada, o time, em uma rápida reunião com o Product Owner, analisam a solicitação de mudança, podendo ser aprovada ou não, e, sendo aprovada, decidem em que provável momento ela será feita.

O registro de solicitações de mudanças deve ser feito através do JIRA. 

O fluxo e os estados estão representados na imagem abaixo:  
 

![Fluxo de Solicitações de Mudanças](https://github.com/thaisdealmeida/fa7-gcs-trabalho/blob/Thais/Fluxo%20-%20Solicita%C3%A7%C3%A3o%20de%20Mudan%C3%A7a.png)

Os possíveis estados para uma mudança estão especificados na tabela abaixo:

| Estado | Descrição |
|-----------|-----------|
| Nova | A solicitação de mudança foi criada. |
| Em Análise | A solicitação está sendo analisada pelo time e pelo Product Owner, caso seja necessário. |
| Recusada | A solicitação foi recusada. |
| Aprovada | A solicitação foi aprovada. |
| Em Desenvolvimento | A mudança está sendo implementada pela equipe de desenvolvedores. |
| Em Teste | A mudança está na fase de testes do desenvolvedor ou da equipe de testes. |
| Desenvolvido | Os desenvolvedores terminaram de implementar a mudança e já pode passar para a equipe de testes. |
| Finalizado | A mudança já pode ser entregue ao cliente. |


### 3.2.2 Comitê de Controle de Mudança (CCB)
O CCB é responsável pela aprovação das solicitações de mudança para que sejam incorporadas ao produto através da alteração de uma baseline. Segundo a hierarquia institucional do CCB, o CCB Item será formado pelos responsáveis de cada item de configuração afetado pela solicitação de mudança. O CCB tem como participantes:

| Participantes |
|-----------|
| Coordenador |  
| Líder de Configuração |  


4. Padrões e Procedimentos
==========================
Essa seção destina-se a apresentar os padrões que serão utilizados no projeto. Os padrões devem ser seguidos e qualquer melhoria deve ser informada a todo o time e partes interessadas, a saber, equipe de gerência de configuração e equipe de auditoria de processos, para que possa ser discutida e, talvez, implantada. 

4.1 Identificação de documentos do projeto
--------------------------------------

Os documentos relacionados ao projeto devem seguir um padrão, que deve ser simples. 

A descrição formal deve ser:

(NOME_DO_PROJETO)_(DESCRICAO_SUCINTA_DO_DOCUMENTO)

Ex: Isis_Documento_Visao.doc

Mais uma vez, o padrão pode ser alterado de acordo com a necessidade do projeto.

4.2 Nomenclatura de Branchs
--------------------------------------

A nomenclatura de branchs deve ser bem explícita para que seja possível uma rápida identificação da sua necessidade. Caso identifique-se a impossibilidade de nomeá-lo dessa forma, pode-se usar o código da atividade, gerado pelo JIRA, como nome. 

A descrição formal deve ser:

(MOTIVO_BRANCH)

ou

<CÓDIGO_JIRA>

Ex: mudancaDeFramework OU FM-42

4.3 Versionamento
--------------------------------------

Códigos de versionamento só devem ser usados nos documentos e códigos isolados quando necessários. A ferramenta usada para versionamento, o Git, é suficiente para guardar todo o histórico dos arquivos. Caso haja necessidade explícita de inserir códigos de versionamento nos documentos, o padrão é o que se segue:

(CodVersao).(CodMajor).(CodMinor)

CodVersao - Versão geral do sistema/documento, ditadas por grandes releases;
CodMajor - Código atualizado entre os releases, sempre que há uma nova feature, esse código é atualizado;
CodMinor - Código atualizado com bugfixes.

Os códigos de versionamento são gerados automaticamente por scripts criados pela equipe de configuração. 

Ex: Isis_Documento_Visao_3.11.1.doc

4.4 Tags
--------------------------------------

As tags devem seguir um padrão que também pode mudar caso o time e/ou equipe de configuração sinta necessidade. Tags devem ser marcas entregáveis, logo, deve-se gerar uma tag sempre que qualquer feature for implantada no cliente. Bugfixes não necessitam de tags. 

O padrão é o seguinte:

(IDENTIFICADOR)_(VERSAO)

Ex: EntregaRequisitos_1.0

5. Treinamento e Recursos
=========================
| Treinamento | Objetivo | Público Alvo |
|-----------|-----------|-----------|
| Repositório |  Ensina como acessar o repositório através de uma máquina cliente, como dar os comandos principais do repositório, como incluir novos itens dentro do repositório e também como remover do mesmo. | Toda a equipe. |



6. Auditorias de Configuração
=============================
As auditorias de configuração serão realizadas mensalmente, segundo o calendário abaixo. As não conformidades serão documentadas no relatório de auditoria que está localizado no diretório informado no item 3.1.2. O acompanhamento das correções será feito através de issues cadastradas no jira do projeto.

| Número | Data Prevista | Data Realizada |     Auditor     |
|--------|---------------|----------------|-----------------|
|01|01/10/2014|01/10/2014|André Rocha|
|02|01/11/2014|01/11/2014|André Rocha|
