# Alan Araujo Rodrigues

## Introdução

Trabalho de graduação na modalidade Portfólio dos projetos realizados com a metodologia Aprendizagem por Projetos Integrados (API), necessário como parte dos requisitos para obtenção do título de Tecnólogo em Banco de Dados pela Faculdade de Tecnologia de São José dos Campos.

# Projeto 1: Primeiro semestre

### Empresa parceira  

<p align="center">
    <b>Interno - Fatec</b> 
    <img src="https://github.com/alantrs/Bertoti/blob/fb16a234423d629719a0fa98c0c15c1295ef0420/metodologia/Imagens/Carcara.png" alt="Logo carcara analises">
</p>

## Descrição do projeto

Pandemia Estruturada é um projeto desenvolvido pela Carcará Analysis, que tem como objetivo analisar os dados oficiais da COVID-19 no Estado de São Paulo e entregá-los ao usuário de forma clara e contextualizada, através de visualizações gráficas ou não-gráficas.

## Tecnologias utilizadas

- **Python**: Python é reconhecida por sua sintaxe simples e legibilidade, tornando-a uma escolha ideal para iniciantes em programação. Amplamente aplicada em diversos campos, como ciência de dados, desenvolvimento web e inteligência artificial, a linguagem destaca-se por sua versatilidade. Sendo interpretada, o código é executado linha por linha, eliminando a necessidade de compilação. Além disso, por ser uma linguagem de alto nível, mais próxima da linguagem humana, a programação em Python é intuitiva e acessível a um amplo público.

- **Html, Css**: HTML (Hypertext Markup Language) e CSS (Cascading Style Sheets) desempenham papéis cruciais no design web. HTML é a espinha dorsal, estruturando o conteúdo da página, enquanto CSS dá vida ao visual, controlando cores, fontes e layout. A combinação destas linguagens permite a criação de interfaces atraentes e organizadas, proporcionando uma experiência de usuário consistente. HTML e CSS são essenciais para a construção de páginas web dinâmicas e visualmente agradáveis.

## Contribuições pessoais

Esse foi o primeiro projeto que tive contato com programação. Fui responsável por auxiliar em tarefas em geral, como ajudar na definição do backlog, levantar requisitos, organizar o github, ajudar no desenvolvimento com python.

## Aprendizados efetivos

Aprendi a introdução aos algoritmos com Python, noções de versionamento de código com git. Também aprendi a introdução de metodologias ágeis no desenvolvimento.
<br>
<details>
<summary>Algoritmos</summary>
<br>
<Ul>
<Li>Lógica de programação</Li>
<Li>Definir variáveis</Li>
<Li>Estrutura de condicionais</Li>
<Li>Input e output de dados</Li>
</Ul>
</details>

<details>
<summary>Scrum</summary>
<br>
<Ul>
<Li>Tipos de papéis no scrum</Li>
<Li>Processos</Li>
</Ul>
 </details>

    
    
# Projeto 2: Segundo semestre

### Empresa parceira  

<p align="center">
    <b>Dom Rock</b>
</br>
    <img src="https://github.com/alantrs/Bertoti/blob/efd7a4e3055f78276feb65f55b0702623e0f2636/metodologia/Imagens/domrock2.png" alt="Logo dom rock">
</p>


## Descrição do projeto

Este projeto visa gerenciar a ativação de clientes na plataforma Dom Rock. A solução proposta concentra-se na entrada de dados, incluindo parâmetros e variáveis específicas de cada cliente, para efetuar a alocação adequada de recursos na plataforma. A abordagem inclui a estimativa de consumo de recursos, considerando fatores como o volume de dados do cliente e o número de usuários. Adicionalmente, a solução é projetada para gerar relatórios e consultas. 

## Tecnologias utilizadas

- **Java**: Linguagem orientada a objetos, foi escolhida para o desenvolvimento do back-end devido à familiaridade prévia da equipe, ampla utilização no mercado e extensa documentação, facilitando a implementação do projeto.

- **PostgreSQL**: PostgreSQL é um sistema de gerenciamento de banco de dados relacional de código aberto que é amplamente utilizado em aplicações empresariais e científicas, devido à sua confiabilidade, escalabilidade e recursos avançados. Além disso, o PostgreSQL é compatível com muitas linguagens de programação, incluindo Java, que foi usada neste projeto.

## Contribuições pessoais

Fui o administrador do banco de dados da equipe. Desenvolvi a modelagem de dados e a criação da base de dados por completo. Ajudei a equipe de backend sendo solicitado por melhorias na distribuição dos dados promovendo a maior facilidade para manipulação dos mesmos.
<br>
    <details>
<summary>Modelagem do banco de dados</summary>
<br>
        
Nesse projeto, o objetivo da modelagem de dados foi representar os dados inseridos pelo cliente e como seria distribuido na nossa base. Utilizou-se o Modelo Entidade-Relacionamento (MER) como uma representação visual para entender a distribuição das tabelas com seus atributos e relacionamento entre elas.

![Modelagem do banco de dados](https://github.com/alantrs/Bertoti/blob/778fd69f6e9fecddd2342af75295ff9542562f1e/metodologia/Imagens/modelagem-domrock.jpeg)
</details>

<details>
      <summary>Implementação física do banco de dados (criar as tabelas, definir as colunas, os tipos de dados, as chaves primárias, as chaves estrangeiras e as restrições necessárias para cada tabela).</summary>
      <br>
    A implementação física é uma etapa fundamental na modelagem de dados, pois envolve a tradução do modelo conceitual em uma estrutura de dados real e eficiente para armazenar e processar os dados em um sistema de banco de dados. Ela é importante para garantir a eficiência, a integridade, a segurança e o desempenho do banco de dados, bem como sua escalabilidade e facilidade de manutenção.

    ```SQL

    CREATE TABLE public.cliente
    (
        id_cliente serial NOT NULL,
        cnpj_cliente character varying COLLATE pg_catalog."default" NOT NULL,
        nome_empresa character varying COLLATE pg_catalog."default" NOT NULL,
        objetivo_negocio character varying COLLATE pg_catalog."default" NOT NULL,
        data_hora_cadastro timestamp not null default CURRENT_TIMESTAMP(1),
        CONSTRAINT cliente_pkey PRIMARY KEY (cnpj_cliente)
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.cliente
        OWNER to postgres;
    	
    
    CREATE TABLE public.produto
    (
        solucao character varying COLLATE pg_catalog."default" NOT NULL,
        nome_produto character varying COLLATE pg_catalog."default" NOT NULL,
        id_produto serial NOT NULL,
        CONSTRAINT produto_pkey PRIMARY KEY (id_produto),
        CONSTRAINT produto_nome_produto_key UNIQUE (nome_produto)
    
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.produto
        OWNER to postgres;
    
    CREATE TABLE public.funcionalidade
    (
        id_funcionalidade serial NOT NULL,
        nome_funcionalidade character varying COLLATE pg_catalog."default" NOT NULL,
        CONSTRAINT funcionalidade_pkey PRIMARY KEY (id_funcionalidade),
        CONSTRAINT funcionalidade_nome_funcionalidade_key UNIQUE (nome_funcionalidade)
    
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.funcionalidade
        OWNER to postgres;
    	
    CREATE TABLE public.core
    (
        id_core serial NOT NULL,
        nome_core character varying COLLATE pg_catalog."default" NOT NULL,
        
        CONSTRAINT core_pkey PRIMARY KEY (id_core),
        CONSTRAINT core_nome_core_unique UNIQUE (nome_core)
    
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.core
        OWNER to postgres;
    
    CREATE TABLE public.origem_dado
    (
        id_origem serial NOT NULL,
        nome_origem character varying COLLATE pg_catalog."default" NOT NULL,
        CONSTRAINT origem_dado_pkey PRIMARY KEY (id_origem),
        CONSTRAINT origem_dado_nome_origem_unique UNIQUE (nome_origem)
    
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.origem_dado
        OWNER to postgres;
    
    CREATE TABLE public.formato
    (
        id_formato serial NOT NULL,
        nome_formato character varying COLLATE pg_catalog."default" NOT NULL,
        CONSTRAINT formato_pkey PRIMARY KEY (id_formato),
        CONSTRAINT formato_nome_formato_unique UNIQUE (nome_formato)
    
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.formato
        OWNER to postgres;
    
    CREATE TABLE public.sistema
    (
        id_sistema serial NOT NULL,
        nome_sistema character varying COLLATE pg_catalog."default" NOT NULL,
        CONSTRAINT sistema_pkey PRIMARY KEY (id_sistema),
        CONSTRAINT sistema_nome_sistema_unique UNIQUE (nome_sistema)
    
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.sistema
        OWNER to postgres;
    
    CREATE TABLE public.cadastro_escopo
    (
        id serial NOT NULL,
        cnpj character varying(20) COLLATE pg_catalog."default" NOT NULL,
        entregavel_min character varying(100) COLLATE pg_catalog."default" NOT NULL,
        entregaveis_possi character varying(100) COLLATE pg_catalog."default" NOT NULL,
        produto character varying(50) COLLATE pg_catalog."default" NOT NULL,
        estrutura character varying(50) COLLATE pg_catalog."default" NOT NULL,
        volume character varying(20) COLLATE pg_catalog."default" NOT NULL,
        funcionalidade character varying(100) COLLATE pg_catalog."default" NOT NULL,
        core character varying(20) COLLATE pg_catalog."default" NOT NULL,
        CONSTRAINT cadastro_escopo_pkey PRIMARY KEY (id)
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.cadastro_escopo
        OWNER to postgres;
    
    
    CREATE TABLE public.bronze
    (
        id_bronze serial NOT NULL,
        cnpj character varying COLLATE pg_catalog."default" NOT NULL,
        origem character varying COLLATE pg_catalog."default" NOT NULL,
        formato character varying COLLATE pg_catalog."default" NOT NULL,
        volume character varying COLLATE pg_catalog."default" NOT NULL,
        frequencia character varying COLLATE pg_catalog."default" NOT NULL,
        sistema character varying COLLATE pg_catalog."default" NOT NULL,
        CONSTRAINT bronze_pkey PRIMARY KEY (id_bronze)
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.bronze
        OWNER to postgres;
    
    CREATE TABLE public.usuario
    (
        id serial NOT NULL,
        usuario character varying(20) COLLATE pg_catalog."default" NOT NULL,
        senha character varying(20) COLLATE pg_catalog."default" NOT NULL,
        nivelacesso character varying(20) COLLATE pg_catalog."default" NOT NULL,
        CONSTRAINT usuario_pkey PRIMARY KEY (id)
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.usuario
        OWNER to postgres;
    
    
    CREATE TABLE public.silver
    (
        id_silver serial NOT NULL,
        nomesilver character varying COLLATE pg_catalog."default",
        status character varying COLLATE pg_catalog."default",
        problema character varying COLLATE pg_catalog."default",
        cnpjsilver character varying COLLATE pg_catalog."default",
        CONSTRAINT silver_pkey PRIMARY KEY (id_silver)
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.silver
        OWNER to postgres;
    
    CREATE TABLE public.gold
    (
    	id serial NOT NULL,
        tiposilver character varying COLLATE pg_catalog."default",
        nomegold character varying COLLATE pg_catalog."default",
        cnpj character varying COLLATE pg_catalog."default",
        CONSTRAINT gold_pkey PRIMARY KEY (id)
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;
    
    ALTER TABLE public.gold
        OWNER to postgres;

    ```
    
 </details>

## Aprendizados efetivos

Aprendi a base para criar um banco de dados. Como iniciar uma modelagem de dados, definir cardinalidades e tranformar o modelo conceitual em script SQL. Aprendi alguns comandos básicos para trabalhar com versionamento de código com Git.

<details>
  <summary>Modelagem de dados</summary>
    <br>
  <ul>
    <li>Estrutura do banco, distribuição das tabelas</li>
    <Li>Cardinalidade</Li>
    <Li>Modelo conceitual, Modelo lógico e Modelo físico</Li>
    <Li>Criar script</Li>
    <Li>Realizar querys</Li>
  </ul>
 </details>

 <details>
  <summary>Versionamento de código</summary>
     <br>
  <ul>
    <li>Comandos básicos: git add, git commit, git pull, git push</li>
    <Li>Criar branches</Li>
  </ul>
 </details>


# Projeto 3: Terceiro semestre

### Empresa parceira  

<p align="center">
    <b>IACIT soluções tecnológicas S.A.</b> 
    <img src="https://github.com/alantrs/Bertoti/blob/ce55d69f624ba22495bcf76f626bb86899750763/metodologia/Imagens/Iacit.png" alt="Logo da IACIT soluções tecnológicas">
</p>


## Descrição do projeto

Foi proposto um desafio para desenvolver um sistema capaz de importar dados meteorológicos de arquivos CSV disponibilizados pela empresa, armazená-los em uma base de dados e gerar relatórios solicitados pelos clientes da empresa IACIT. A aplicação web é capaz filtrar os registros por regiões, estados, estações, tipo de dado e ranges de datas, além de exibir as informações em formato de gráficos e cards. Por fim, é possível obter relatórios com base na pesquisa realizada.

 - `Requisitos funcionais exigidos:` Cadastro de estações, cadastro de estados e regiões, importação de dados e geração de relatórios.
 - `Requisitos não funcionais exigidos:` Sistema Web, linguagem java, banco de dados relacional e documentações.
 
 ## Tecnologias utilizadas

 
- **Java e Spring boot**: A linguagem Java foi utilizada para desenvolver todo o back-end da aplicação, utilizando o framework Spring Boot. O Spring Boot é uma estrutura que permite aos desenvolvedores criar rapidamente aplicativos web em Java, fornecendo um conjunto de ferramentas e bibliotecas que tornam a construção de aplicativos mais rápida e fácil.

- **PostgreSQL**: PostgreSQL é um sistema de gerenciamento de banco de dados relacional de código aberto que é amplamente utilizado em aplicações empresariais e científicas, devido à sua confiabilidade, escalabilidade e recursos avançados. Além disso, o PostgreSQL é compatível com muitas linguagens de programação, incluindo Java, que foi usada neste projeto.

- **Html, Css, Javascript**: As linguagens de marcação HTML e CSS foram utilizadas em conjunto com a linguagem de programação JavaScript para criar a interface gráfica da aplicação. O HTML é a base da estrutura da página web, enquanto o CSS é responsável por definir o estilo visual e a aparência da página. O JavaScript é utilizado para adicionar interatividade à página, permitindo que o usuário realize ações e que os dados sejam exibidos e atualizados dinamicamente.
Com o uso do HTML, CSS e JavaScript, foi possível criar uma interface amigável e intuitiva para os usuários da aplicação, permitindo que eles possam visualizar os dados meteorológicos e gerar relatórios de forma fácil e eficiente. Além disso, utilizamos uma biblioteca do javascript chamada Charts, perfeita para disponibilizar os dados em forma de gráficos.

## Contribuições pessoais

Fui o administrador do banco de dados da equipe em conjunto com a função de Scrum master. Como DBA desenvolvi desde a modelagem de dados até a criação da base de dados completa. Como scrum master fui responsável por garantir que o processo Scrum estivesse sendo seguido corretamente e que a equipe estivesse funcionando de maneira eficaz e produtiva.
<br>
    <details>
<summary>Modelagem do banco de dados.</summary>
<br>

No caso deste projeto, o objetivo da modelagem de dados foi representar os dados meteorológicos, como temperatura, umidade e outros indicadores. Utilizou-se o Modelo Entidade-Relacionamento (MER) como uma representação visual para entender a distribuição das tabelas com seus atributos e relacionamento entre elas.

![Modelagem do banco de dados](https://github.com/alantrs/Bertoti/blob/e19d9567debe132ef4387b306ba9451d048716cf/metodologia/Imagens/modelagem_img1.jpeg)
</details>

    
   <details>
      <summary>Implementação física do banco de dados (criar as tabelas, definir as colunas, os tipos de dados, as chaves primárias, as chaves estrangeiras e as restrições necessárias para cada tabela).</summary>
      <br>
    A implementação física é uma etapa fundamental na modelagem de dados, pois envolve a tradução do modelo conceitual em uma estrutura de dados real e eficiente para armazenar e processar os dados em um sistema de banco de dados. Ela é importante para garantir a eficiência, a integridade, a segurança e o desempenho do banco de dados, bem como sua escalabilidade e facilidade de manutenção.
    
```SQL
    
CREATE TABLE regiao (
    regiao_id serial,
    nome_regiao VARCHAR,
    CONSTRAINT pk_regiao_id PRIMARY KEY (regiao_id),
    CONSTRAINT unique_regiao UNIQUE (nome_regiao)
);
CREATE TABLE estado (
    estado_id serial,
    nome_estado VARCHAR,
    fk_regiao_nome_regiao VARCHAR,
    CONSTRAINT pk_estado_id PRIMARY KEY (estado_id),
    CONSTRAINT fk_estado FOREIGN KEY (fk_regiao_nome_regiao)
               REFERENCES regiao (nome_regiao),
    CONSTRAINT unique_estado UNIQUE (nome_estado)
);
CREATE TABLE estacao (
    nome_estacao VARCHAR,
    cod_wmo VARCHAR,
    latitude NUMERIC,
    longitude VARCHAR,
    altitude NUMERIC,
    data_fundacao DATE,
    fk_estado_nome_estado VARCHAR,
    CONSTRAINT pk_cod_wmo PRIMARY KEY (cod_wmo),
    CONSTRAINT fk_estacao FOREIGN KEY (fk_estado_nome_estado)
               REFERENCES estado (nome_estado)	
);
CREATE TABLE precipitacao (
    prec_id serial,
    prec_data DATE,
    prec_hora TIME,
    prec_total NUMERIC,
    fk_estacao_cod_wmo VARCHAR,
    CONSTRAINT pk_prec_id PRIMARY KEY (prec_id),
    CONSTRAINT fk_precipitacao FOREIGN KEY (fk_estacao_cod_wmo)
               REFERENCES estacao (cod_wmo)
);
CREATE TABLE pressao_atmosferica (
    pre_atm_id serial,
    pre_data DATE,
    pre_hora TIME,
    pre_atm_estacao NUMERIC,
    pre_atm_max NUMERIC,
    pre_atm_min NUMERIC,
    fk_estacao_cod_wmo VARCHAR,
    CONSTRAINT pk_pre_atm_id PRIMARY KEY (pre_atm_id),
    CONSTRAINT fk_pressao_atmosferica FOREIGN KEY (fk_estacao_cod_wmo)
               REFERENCES estacao (cod_wmo)
);
CREATE TABLE radiacao_global (
    rad_id serial,
    rad_data DATE,
    rad_hora TIME,
    rad_global NUMERIC,
    fk_estacao_cod_wmo VARCHAR,
    CONSTRAINT pk_rad_id PRIMARY KEY (rad_id),
    CONSTRAINT fk_radiacao_global FOREIGN KEY (fk_estacao_cod_wmo)
               REFERENCES estacao (cod_wmo)
);
CREATE TABLE temperatura (
    temp_id serial,
    temp_data DATE,
    temp_hora TIME,
    temp_ar NUMERIC,
    temp_ponto_orvalho NUMERIC,
    temp_max NUMERIC,
    temp_min NUMERIC,
    temp_orvalho_max NUMERIC,
    temp_orvalho_min NUMERIC,
    fk_estacao_cod_wmo VARCHAR,
    CONSTRAINT pk_temp_id PRIMARY KEY (temp_id),
    CONSTRAINT fk_temperatura FOREIGN KEY (fk_estacao_cod_wmo)
               REFERENCES estacao (cod_wmo)
);
CREATE TABLE umidade (
    umi_id serial,
    umi_data DATE,
    umi_hora TIME,
    umi_rel_max NUMERIC,
    umi_rel_min NUMERIC,
    umi_rel_ar NUMERIC,
    fk_estacao_cod_wmo VARCHAR,
    CONSTRAINT pk_umi_id PRIMARY KEY (umi_id),
    CONSTRAINT fk_umidade FOREIGN KEY (fk_estacao_cod_wmo)
               REFERENCES estacao (cod_wmo)
);
CREATE TABLE vento (
    ven_id serial,
    ven_data DATE,
    ven_hora TIME,
    ven_direcao_hor NUMERIC,
    ven_rajada_max NUMERIC,
    ven_velocidade_hor NUMERIC,
    fk_estacao_cod_wmo VARCHAR,
    CONSTRAINT pk_ven_id PRIMARY KEY (ven_id),
    CONSTRAINT fk_vento FOREIGN KEY (fk_estacao_cod_wmo)
               REFERENCES estacao (cod_wmo)
);

```
    
 </details>
   
<details>
  <summary style="background-color: lightgray; padding: 5px;">Gerar backup.</summary>
    <br>
    Backup é um processo essencial para proteger e preservar dados importantes. Ele permite recuperar informações perdidas devido a falhas de hardware, erros humanos, ataques cibernéticos ou desastres naturais. No nosso projeto foram realizados backups a cada sprint, para garantir a integridade e segurança dos dados. O backup era gerado por esse simples comando.
  <br>
  <p style="margin-left: 20px;">
    <code>pg_dump -U postgres -d iacit -F p -f "C:backup_iacit.sql"</code>
  </p>
</details>

<details>
  <summary>Algumas das minhas contribuições como Master:</summary>
 <br>
 <ul>
    <li>Garantir que a equipe esteja seguindo os princípios do Scrum e entendendo seus papéis e responsabilidades.</li>
    <li>Organizar e facilitar as reuniões do Scrum</li>
    <li>Ajudar a equipe a criar e manter o Backlog do Produto, garantindo que esteja atualizado e priorizado corretamente.</li>
    <li>Remover impedimentos que possam impedir a equipe de concluir as tarefas necessárias para atingir os objetivos do Sprint.</li>
    <li>Monitorar o progresso da equipe e garantir que ela esteja cumprindo os prazos e entregando os itens do Backlog do Produto dentro do prazo.</li>
    <li>Fornecer feedback regular aos membros da equipe e ajudá-los a melhorar continuamente o seu processo de trabalho.</li>
    <li>Garantir uma comunicação eficaz entre todos os membros da equipe, incluindo o Product Owner, os desenvolvedores e outras partes interessadas.</li>
    <li>Promover um ambiente de trabalho positivo e colaborativo para a equipe.</li>
  </ul>
</details>


## Aprendizados efetivos

Como DBA, adquiri conhecimentos em modelagem de dados, arquitetura do SGBD PostgreSQL, e aprofundei meus conhecimentos em SQL incluindo comandos DDL, DML e DCL. Como Scrum Master, desenvolvi habilidades valiosas em liderança, facilitação do processo Scrum, remoção de impedimentos, comunicação, feedback e melhoria contínua.

<details>
  <summary>Modelagem de dados</summary>
    <br>
  <ul>
    <li>Estrutura do banco, distribuição das tabelas</li>
    <li>Normalização</li>
    <Li>Constraints</Li>
  </ul>
 </details>
<details>
  <summary>SQL</summary>
    <br>
  <ul>
    <li>DDL (Data Definition Language)</li>
    <li>DML (Data Manipulation Language)</li>
    <li>DCL (Data Control Language)</li>
  </ul>
 </details>
 <details>
  <summary>Administração do PostgreSQL</summary>
     <br>
  <ul>
    <li>Política de backup</li>
    <li>Criação de usuário</li>
  </ul>
 </details>

<details>
  <summary>Domínio do processo Scrum</summary>
  <ul>
    <li>Compreensão dos princípios e papéis do Scrum.</li>
   <li>Remoção de impedimentos</li>
   <li>Comunicação e colaboração</li>
   <li>Feedback e melhoria contínua</li>
   <li>Habilidades de liderança e organização</li>
  </ul>
 </details>


# Projeto 4: Quarto semestre

### Empresa parceira

<p align="center">
    <b>Embraer</b> 
    <img src="https://github.com/alantrs/Bertoti/blob/09db3eee9ca94737bc0fc52ef7fc1313ae6cdf71/metodologia/Imagens/embraer.png" alt="Logo embraer">
</p>

## Descrição do projeto

## Tecnologias utilizadas

- **Java e Spring boot**: A linguagem Java foi utilizada para desenvolver todo o back-end da aplicação, utilizando o framework Spring Boot. O Spring Boot é uma estrutura que permite aos desenvolvedores criar rapidamente aplicativos web em Java, fornecendo um conjunto de ferramentas e bibliotecas que tornam a construção de aplicativos mais rápida e fácil.

- **Vue.js**: Vue.js é um framework de desenvolvimento web de código aberto e progressivo. Sua arquitetura centrada em componentes oferece uma abordagem modular que facilita a construção eficiente de aplicativos complexos.

- **AutonomOus Database Oracle**: O Oracle Autonomous Database é uma solução de banco de dados em nuvem que se destaca pela automação completa, autogerenciamento e uso de machine learning. Elimina tarefas manuais, otimiza o desempenho, garante segurança e oferece escalabilidade automática, proporcionando eficiência e economia de custos. 

## Contribuições pessoais

Nesse projeto fui novamente o DBA da equipe. Desenvolvi toda estrutura da base de dados, configurei a regra de negócio na propria base. Apliquei funções e procedures para tratamento da logica de instalação de itens em uma aeronave. Apliquei o uso de triggers para fins de auditoria para captar eventos. Apliquei o uso de views para visualização de dados.
<br>
    <details>
<summary>Modelagem do banco de dados</summary>
<br>

No caso deste projeto, o objetivo da modelagem de dados foi representar os dados de boletins de serviço, itens e chassi. Utilizou-se o Modelo Entidade-Relacionamento (MER) como uma representação visual para entender a distribuição das tabelas com seus atributos e relacionamento entre elas.

![Modelagem do banco de dados](https://github.com/alantrs/Bertoti/blob/7f11e2e448aaac2afb7da5aab6d272305d2051aa/metodologia/Imagens/diagrama-embraer.jpg)
</details>

<details>
<br>
<summary>Funções e procedures</summary>
</details>

<details>
<br>
<summary>Triggers</summary>
</details>


<details>
<br>
<summary>Views</summary>

Essa view retorna um caminho hierarquico das lógicas, facilitando o tratamento para o backend, onde é possivel definir uma entrada (buscando a dependencia ou buscando pelo nivel) para recuperar a lógica de aplicação de um determinado item.

    ```SQL
    -- view que retorna o caminho hierarquico das logicas
    CREATE OR REPLACE VIEW v_hierarquia AS SELECT id_logica, logica_boletim.id_Item, ITEM.NOME, input1, operacao,  input2, dependencia,  LEVEL AS nivel, 
    CONNECT_BY_ROOT(ID_logica) AS no_raiz, SYS_CONNECT_BY_PATH(ID_logica, '/') AS caminho_hierarquia
    FROM Logica_Boletim
    JOIN item ON logica_boletim.id_item = item.id_item
    START WITH dependencia IS NULL
    CONNECT BY PRIOR ID_logica = dependencia;

    ```
</details>




## Aprendizados efetivos

Este projeto proporcionou a oportunidade de aprendizado sobre tópicos avançados em banco de dados. Durante o desenvolvimento, adquiri habilidades como a criação e execução de funções e procedimentos, o que me permitiu entender melhor a manipulação e gestão de dados.
Tive a oportunidade de trabalhar com auditoria usando triggers, o que me deu uma visão mais profunda sobre a segurança e integridade dos dados. Além disso, a visualização de dados com views me permitiu entender como apresentar dados de uma maneira mais eficiente e eficaz.
Aprofundei meus conhecimentos na linguagem PL/SQL da Oracle, o que me permitiu desenvolver soluções mais robustas e eficientes.

  <details>
  <summary>Configuração de conexão com Autonomous database</summary>
     <br>
  <ul>
    <li>Criação da wallet de conexão</li>
    <li>Liberação de consultas REST</li>
  </ul>
 </details>
 <details>
  <summary>Criação de funções e procedures com PL/SQL</summary>
     <br>
  <ul>
    <li>Estrutura de uma função</li>
    <li>Estrutura de uma procedure</li>
    <Li>Como executar funções e procedures</Li>
  </ul>
 </details>

  <details>
  <summary>Uso de triggers</summary>
     <br>
  <ul>
    <li>Estrutura de uma trigger</li>
    <li>Utilização e vantagens</li>
  </ul>
 </details>

   <details>
  <summary>Uso de views</summary>
     <br>
  <ul>
    <li>Estrutura de uma view</li>
    <li>Utilização e vantagens</li>
    <Li>View hierarquica no oracle</Li>
  </ul>
 </details>






 
 
 
 
 
 



