<Nome do Projeto>
=================
Plano de Gerenciamento de Configuração
======================================
Versão 1.1
------------------

_[Observação: O template a seguir é fornecido para uso com o Rational Unified Process (RUP).  O texto exibido entre colchetes e em itálico foi incluído para orientar o autor e deve ser excluído antes da publicação do documento._

_Este documento utiliza a formatação da linguagem [Markdown] (http://daringfireball.net/projects/markdown/). Você pode encontrar um guia de referência rápido [aqui] (https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).]_

Histórico de Versões
--------------------

|Data                |Versão       |Descrição               |Autor          |
|--------------------|-------------|------------------------|---------------|
|13/12/2014 | 1.0 | Versão inicial. | Thaís de Almeida |
|14/12/2014 | 1.1 | Inclusão de Seção 4. | Thaís de Almeida |
|14/12/2014 | 1.2 | Inclusão de Seção 1.3, 3.1.3 e 6 | André rocha |
|14/12/2014 | 1.3 | Inclusão de Seção 1.1, 3.2.2 e 5 | Manoela Freitas |
|15/12/2014 | 1.4 | Inclusão de Seção 1.2, 1.5, 2.1 e 3.1.4 | Fernando Freitas |
|_&lt;dd/mm/aaaa&gt;_|_&lt;1.1&gt;_|_&lt;Outra versão&gt;_  |_&lt;autor&gt;_|



1. Introdução
==============

_[A introdução do Plano de Gerenciamento de Configuração  oferece uma visão geral de todo o documento. 
Ela inclui a finalidade, o escopo, as definições, os acrônimos, as abreviações, as referências e uma visão geral deste
Plano de Gerenciamento de Configuração.]_

1.1 Finalidade
---------------
Este documento tem o objetivo de descrever o plano de Gestão de Configuração e Mudança para o estabelecimento da configuração do projeto Biblioteca.

1.2 Escopo
----------
Este documento é destinado a todos os integrantes da equipe responsável pelo projeto Biblioteca e abrange todo o controle e gerenciamento da configuração do projeto, tais como requisitos, casos de uso, diagramas, arquivos de código-fonte, modelos de dados, casos de teste e manuais.

1.3 Definições, Acrônimos e Abreviações
---------------------------------------
 NOMN - Nome do projeto, acronimo utilizado no inicio do nome de todos os artefatos.
 Jira - Ferramenta da Atlassian para controle de mudanças.
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
|CCM|Manoela Freitas|Estabelecer Processo de Controle de Mudanças <br> Revisar Solicitação de Mudança <br> Aprovar ou rejeitar solicitações de mudanças|
|Desenvolvedor|Fernando Italo, <br> Andre Rocha|Seguir os padrões e procedimentos definidos no plano de gerência de configuração|

2.2 Ferramentas, Ambiente e Infra-estrutura
-------------------------------------------
_[Descreva o ambiente de computação e as ferramentas de software a serem utilizadas para desempenhar as funções de CM em todo o ciclo de vida do projeto ou produto._
_Descreva as ferramentas e os procedimentos necessários utilizados para o controle de versão dos itens de configuração gerados no ciclo de vida do projeto ou produto._
_As questões envolvidas na configuração do ambiente de CM incluem:_
* _tamanho previsto dos dados do produto_
* _distribuição da equipe do produto_
* _localização física dos servidores e clientes]_
 


3. O Programa de Gerenciamento de Configuração
==============================================

3.1 Identificação da Configuração
---------------------------------
### 3.1.1 Métodos de Identificação
----------------------------------
_[Descreva como os artefatos do projeto ou produto devem ser nomeados, marcados e numerados. O esquema de identificação deve abranger o hardware, o software do sistema, os produtos de terceiros (COTS) e todos os artefatos de desenvolvimento de aplicativos listados na estrutura de diretórios do produto; por exemplo, planos, modelos, componentes, software de teste, resultados e dados, executáveis e assim por diante.]_

### 3.1.2 Itens de Configuração
_[Relacionar os artefatos ou grupos de artefatos, separando por tipo, modulo ou subsistema, responsável ou momento em que deverão ser incluídos em baselines._
* _“Inclusão em Baseline” em branco significa que o grupo de artefatos não participará de baseline. Pode ser expresso como uma data ou identificador de uma baseline, fase ou ponto de controle_
* _“Responsável”: indicar nominalmente, sempre que possível]_

| Item (ou Tipo de Item)                 | Responsável na equipe	     | Inclusão em Baseline |
|----------------------------------------|-----------------------------|----------------------|
|_&lt;grupo de itens de configuração&gt;_|_&lt;nome do responsável&gt;_|_&lt;momento a partir do qual o conjunto de artefatos será incluído em baseline&gt;_|



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
