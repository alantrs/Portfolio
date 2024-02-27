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

- **Python e Flask**: Python, uma linguagem conhecida por sua simplicidade e versatilidade, é escolhida como base para o desenvolvimento. Flask, um framework web em Python, é incorporado para facilitar a criação de aplicativos web. Flask oferece estruturas mínimas, permitindo flexibilidade e modularidade no desenvolvimento de aplicações web. Sua integração com Python torna o Flask uma escolha popular para criar APIs e páginas web dinâmicas.

- **Html, Css**: HTML (Hypertext Markup Language) e CSS (Cascading Style Sheets) desempenham papéis cruciais no design web. HTML é a espinha dorsal, estruturando o conteúdo da página, enquanto CSS dá vida ao visual, controlando cores, fontes e layout. A combinação destas linguagens permite a criação de interfaces atraentes e organizadas, proporcionando uma experiência de usuário consistente. HTML e CSS são essenciais para a construção de páginas web dinâmicas e visualmente agradáveis.

## Contribuições pessoais

Esse foi o primeiro projeto que tive contato com programação. Minha contribuição envolveu uma participação em varias áreas, desde auxiliar em tarefas em geral, como ajudar na definição do backlog, organizar o repositório e também desenvolver com python.
<br>
<details>
  <summary><b>Gráfico total de óbitos</b></summary>
  <br>
  Uma funcionalidade que ajudei a desenvolver foi o endpoint para gerar um gráfico de totalidade de óbitos. O método gera um gráfico de linha mostrando o crescimento dos óbitos, realiza personalizações visuais, calcula estatísticas como o número máximo de óbitos e a letalidade, e renderiza essas informações em uma página web. A finalidade é proporcionar uma representação visual e interativa dos dados, permitindo aos usuários compreenderem a situação da pandemia na região.

    ```python
    
        # Gráfico total de óbitos
            fig4 = px.line(covidsp.sort_values(by=['Data'], ascending=[True]), x='Data', y='Total de óbitos',
                           line_shape='linear', template='xgridoff', color_discrete_sequence=palette,
                           line_dash_sequence=['solid'],
                           render_mode='auto', hover_data=['Data', 'Total de óbitos', 'Óbitos por dia'],
                           title='<b>Crescimento do nº de óbitos no Estado</b>')
            fig4.update_traces(line=dict(width=6)),
            fig4.update_yaxes(showgrid=True, gridcolor='rgba(0, 0, 0, 0.2)', tickmode="linear", tick0=0, dtick=15000),
            fig4.update_xaxes(tickangle=-45),
            fig4.update_layout(autosize=True, height=700, margin=dict(t=85, b=90, l=100, r=40),
                               xaxis_title='', yaxis_title="Total de óbitos",
                               plot_bgcolor='#ffffff', paper_bgcolor='#ffffff',
                               title_font=dict(size=32, color='#dc770d', family="Helvetica, neue"),
                               font=dict(size=18, color='#dc770d', family="Helvetica, neue"),
                               xaxis_tickformat='%b %d,<br>%y', xaxis_hoverformat='%b %d, %Y')
            graf4 = fig4.to_html(full_html=False)
            obtotal = covidsp['Total de óbitos'].max()
            casostotal = covidsp['Total de casos'].max()
            let = (obtotal / casostotal) * 100
            info4 = "{:.2f}".format(let).replace('.', ',')
            if info4 == inf:
                info4 = 0
            if info4 == 'nan':
                info4 = 0

            return render_template('estados.html', form=form, min=mini, max=maxi,
                                   start=form_start[-1], end=form_end[-1],
                                   graf1_covidsp=graf1, graf2_covidsp=graf2, graf3_covidsp=graf3, graf4_covidsp=graf4,
                                   painel1_covidsp=casost, painel2_covidsp=obitost, painel3_covidsp=casosult,
                                   painel4_covidsp=obitosult, info1_covidsp=info1, info2_covidsp=info2,
                                   info3_covidsp=info3, info4_covidsp=info4)
                               
    ```
</details>



## Aprendizados efetivos

Aprendi a introdução aos algoritmos com Python, noções de versionamento de código com git. Também aprendi a introdução de metodologias ágeis no desenvolvimento.
<br>
<details>
<summary><b>Desenvolvimento de software</b></summary>
<br>
<ul>
  <li>Lógica de programação: Entender como funciona o algoritmo</li>
  <li>Definir variáveis</li>
  <li>estruturas de controle de fluxo: if else, while loop, for loop</li>
  <li>Input e output de dados</li>
  <Li>Entender como funciona um framework como o flask</Li>
</ul>
</details>

<details>
<summary><b>Metodologia ágil Scrum</b></summary>
<br>
<ul>
    <Li>Tipos de papéis no scrum</Li>
    <Li>Minimum Viable Product</Li>
</ul>
 </details>
<hr>
    
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
<summary><b>Modelagem do banco de dados</b></summary>
<br>
        
Nesse projeto, o objetivo da modelagem de dados foi representar os dados inseridos pelo cliente e como seria distribuido na nossa base. Utilizou-se o Modelo Entidade-Relacionamento (MER) como uma representação visual para entender a distribuição das tabelas com seus atributos e relacionamento entre elas.

![Modelagem do banco de dados](https://github.com/alantrs/Bertoti/blob/778fd69f6e9fecddd2342af75295ff9542562f1e/metodologia/Imagens/modelagem-domrock.jpeg)
</details>

<details>
      <summary><b>Implementação física do banco de dados</b></summary>
      <br>
    A implementação física é uma etapa fundamental na modelagem de dados, pois envolve a tradução do modelo conceitual em uma estrutura de dados real e eficiente para armazenar e processar os dados em um sistema de banco de dados. Ela é importante para garantir a eficiência, a integridade, a segurança e o desempenho do banco de dados, bem como sua escalabilidade e facilidade de manutenção.

    ```SQL
    CREATE TABLE public.produto
    (
        solucao character varying COLLATE pg_catalog."default" NOT NULL,
        nome_produto character varying COLLATE pg_catalog."default" NOT NULL,
        id_produto serial NOT NULL,
        CONSTRAINT produto_pkey PRIMARY KEY (id_produto),
        CONSTRAINT produto_nome_produto_key UNIQUE (nome_produto)
    
    )
    
    CREATE TABLE public.funcionalidade
    (
        id_funcionalidade serial NOT NULL,
        nome_funcionalidade character varying COLLATE pg_catalog."default" NOT NULL,
        CONSTRAINT funcionalidade_pkey PRIMARY KEY (id_funcionalidade),
        CONSTRAINT funcionalidade_nome_funcionalidade_key UNIQUE (nome_funcionalidade)
    
    )
    	
    CREATE TABLE public.core
    (
        id_core serial NOT NULL,
        nome_core character varying COLLATE pg_catalog."default" NOT NULL,
        
        CONSTRAINT core_pkey PRIMARY KEY (id_core),
        CONSTRAINT core_nome_core_unique UNIQUE (nome_core)
    
    )
    ```
    
 </details>

## Aprendizados efetivos

Aprendi a base para criar um banco de dados. Como iniciar uma modelagem de dados, definir cardinalidades e tranformar o modelo conceitual em script SQL. Aprendi alguns comandos básicos para trabalhar com versionamento de código com Git.

<details>
  <summary><b>Banco de dados</b></summary>
    <br>
  <ul>
    <li>Estrutura do banco, distribuição das tabelas</li>
    <Li>Cardinalidades</Li>
    <Li>Modelo conceitual, Modelo lógico e Modelo físico</Li>
    <Li>Criar script</Li>
    <Li>Realizar querys simples</Li>
  </ul>
 </details>

 <details>
  <summary><b>Versionamento de código</b></summary>
     <br>
  <ul>
    <li>Comandos básicos: git add, git commit, git pull, git push</li>
    <Li>Criar branches</Li>
  </ul>
 </details>

<hr>

# Projeto 3: Terceiro semestre

### Empresa parceira  

<p align="center">
    <b>IACIT soluções tecnológicas S.A.</b> 
    <img src="https://github.com/alantrs/Bertoti/blob/ce55d69f624ba22495bcf76f626bb86899750763/metodologia/Imagens/Iacit.png" alt="Logo da IACIT soluções tecnológicas">
</p>


## Descrição do projeto

Foi proposto um desafio para desenvolver um sistema capaz de importar dados meteorológicos de arquivos CSV disponibilizados pela empresa, armazená-los em uma base de dados e gerar relatórios solicitados pelos clientes da empresa IACIT. A aplicação web é capaz filtrar os registros por regiões, estados, estações, tipo de dado e ranges de datas, além de exibir as informações em formato de gráficos e cards. Por fim, é possível obter relatórios com base na pesquisa realizada.
 
 ## Tecnologias utilizadas

 
- **Java e Spring boot**: A linguagem Java foi utilizada para desenvolver todo o back-end da aplicação, utilizando o framework Spring Boot. O Spring Boot é uma estrutura que permite aos desenvolvedores criar rapidamente aplicativos web em Java, fornecendo um conjunto de ferramentas e bibliotecas que tornam a construção de aplicativos mais rápida e fácil.

- **PostgreSQL**: PostgreSQL é um sistema de gerenciamento de banco de dados relacional de código aberto que é amplamente utilizado em aplicações empresariais e científicas, devido à sua confiabilidade, escalabilidade e recursos avançados. Além disso, o PostgreSQL é compatível com muitas linguagens de programação, incluindo Java, que foi usada neste projeto.

- **Html, Css, Javascript**: As linguagens de marcação HTML e CSS foram utilizadas em conjunto com a linguagem de programação JavaScript para criar a interface gráfica da aplicação. O HTML é a base da estrutura da página web, enquanto o CSS é responsável por definir o estilo visual e a aparência da página. O JavaScript é utilizado para adicionar interatividade à página, permitindo que o usuário realize ações e que os dados sejam exibidos e atualizados dinamicamente.
Com o uso do HTML, CSS e JavaScript, foi possível criar uma interface amigável e intuitiva para os usuários da aplicação, permitindo que eles possam visualizar os dados meteorológicos e gerar relatórios de forma fácil e eficiente. Além disso, utilizamos uma biblioteca do javascript chamada Charts, perfeita para disponibilizar os dados em forma de gráficos.

## Contribuições pessoais

Fui o administrador do banco de dados da equipe em conjunto com a função de Scrum master. Como DBA desenvolvi desde a modelagem de dados até a criação da base de dados completa. Como scrum master fui responsável por garantir que o processo Scrum estivesse sendo seguido corretamente e que a equipe estivesse funcionando de maneira eficaz e produtiva.
<br>
    <details>
<summary><b>Modelagem do banco de dados</b></summary>
<br>

No caso deste projeto, o objetivo da modelagem de dados foi representar os dados meteorológicos, como temperatura, umidade e outros indicadores. Utilizou-se o Modelo Entidade-Relacionamento (MER) como uma representação visual para entender a distribuição das tabelas com seus atributos e relacionamento entre elas.
<br>

![Modelagem do banco de dados](https://github.com/alantrs/Bertoti/blob/e19d9567debe132ef4387b306ba9451d048716cf/metodologia/Imagens/modelagem_img1.jpeg)
</details>

    
   <details>
      <summary><b>Implementação física do banco de dados</b></summary>
      <br>
    A implementação física é uma etapa fundamental na modelagem de dados, pois envolve a tradução do modelo conceitual em uma estrutura de dados real e eficiente para armazenar e processar os dados em um sistema de banco de dados. Ela é importante para garantir a eficiência, a integridade, a segurança e o desempenho do banco de dados, bem como sua escalabilidade e facilidade de manutenção.
    <br>
    
```SQL
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
  <summary><b>Gerar backup</b></summary>
    <br>
    Backup é um processo essencial para proteger e preservar dados importantes. Ele permite recuperar informações perdidas devido a falhas de hardware, erros humanos, ataques cibernéticos ou desastres naturais. No nosso projeto foram realizados backups a cada sprint, para garantir a integridade e segurança dos dados. O backup era gerado por esse simples comando.
  <br>
  <p style="margin-left: 20px;">
    <code>pg_dump -U postgres -d iacit -F p -f "C:backup_iacit.sql"</code>
  </p>
</details>

<details>
  <summary><b>Algumas das minhas contribuições como Master:</b></summary>
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
  <summary><b>Banco de dados</b></summary>
    <br>
  <ul>
    <li>Estrutura do banco postgreSQL</li>
    <li>Normalização</li>
    <Li>Relacionamentos</Li>
    <Li>Constraints</Li>
  </ul>
 </details>
<details>
  <summary><b>SQL</b></summary>
    <br>
  <ul>
    <li>DDL (Data Definition Language)</li>
    <li>DML (Data Manipulation Language)</li>
    <li>DCL (Data Control Language)</li>
    <Li>Querys com joins e funções de agrupamento</Li>
  </ul>
 </details>
 <details>
  <summary><b>Administração do PostgreSQL</b></summary>
     <br>
  <ul>
    <li>Política de backup</li>
    <li>Criação de usuário</li>
    <Li>Definição de roles</Li>
  </ul>
 </details>

<details>
  <summary><b>Domínio do processo Scrum</b></summary>
  <ul>
    <li>Compreensão dos princípios e papéis do Scrum.</li>
   <li>Remoção de impedimentos</li>
   <li>Comunicação e colaboração</li>
   <li>Feedback e melhoria contínua</li>
   <li>Habilidades de liderança e organização</li>
  </ul>
 </details>

<hr>

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

Nesse projeto fui novamente o DBA da equipe. Desenvolvi toda estrutura da base de dados, de forma estratégica para construir um esquema robusto e que comportasse os relacionamentos complexos da melhor forma. Apliquei funções e procedures para tratamento da logica de instalação de itens em uma aeronave. Apliquei o uso de triggers para fins de auditoria para captar eventos. Apliquei o uso de views para visualização de dados.
<br>
    <details>
<summary><b>Modelagem do banco de dados</b></summary>
<br>

No caso deste projeto, o objetivo da modelagem de dados foi representar os dados de boletins de serviço, itens e chassi. Essa modelagem foi estratégica para facilitar a consulta da lógica interna de instalações de itens em uma aeronave. O objetivo central era estruturar as tabelas de maneira que exitisse uma hierarquia de condições recebidas pela empresa, facilitando assim para o backend tratar e ter códigos mais limpos e de fácil manutenção.

![Modelagem do banco de dados](https://github.com/alantrs/Bertoti/blob/7f11e2e448aaac2afb7da5aab6d272305d2051aa/metodologia/Imagens/diagrama-embraer.jpg)
</details>

<details>
<br>
<summary><b>Funções e procedures</b></summary>
<br>
 Essa é uma procedure em PL/SQL que tem como objetivo verificar se determinados itens estão instalados de fábrica em uma aeronave. Ela percorre as tabelas chassi e logica_fabrica e, para cada combinação de chassi e item, utiliza a função verificar_instalacao_fabrica para determinar se o item está instalado.
A lógica principal está na cláusula MERGE, que realiza operações de atualização e inserção na tabela chassi_item. Se houver uma correspondência entre o chassi e o item na tabela chassi_item, ela atualiza o status de instalação. Se não houver correspondência, insere um novo registro indicando se o item está ou não instalado de fábrica.
    
    ```SQL
    CREATE OR REPLACE PROCEDURE verificar_e_inserir_instalacao_fabrica AS
      v_chassi chassi.id_chassi%TYPE;
      v_item logica_fabrica.id_item%TYPE;
      v_instalado NUMBER;
    BEGIN
      FOR r_chassi IN (SELECT id_chassi FROM chassi) LOOP
        FOR r_item IN (SELECT id_item FROM logica_fabrica) LOOP
          v_instalado := verificar_instalacao_fabrica(r_chassi.id_chassi, r_item.id_item);
             MERGE INTO chassi_item ci
              USING (
                SELECT r_chassi.id_chassi AS id_chassi, r_item.id_item AS id_item, v_instalado AS instalado
                FROM dual
              ) temp
              ON (
        ci.id_chassi = temp.id_chassi AND ci.id_item = temp.id_item
      )
      WHEN MATCHED THEN
        UPDATE SET ci.instalado = temp.instalado
      WHEN NOT MATCHED THEN
        INSERT (id_chassi, id_item, instalado)
        VALUES (temp.id_chassi, temp.id_item, temp.instalado);
        END LOOP;
      END LOOP;
    END verificar_e_inserir_instalacao_fabrica;
    /
</details>

<details>
<br>
<summary><b>Triggers</b></summary>
Essa trigger foi criada para realizar auditoria na tabela CHASSI_BOLETIM após operações de atualização no campo STATUS. Quando uma atualização ocorre, a trigger gera um novo identificador de auditoria utilizando a sequência SEQ_CHASSI_BOLETIM_AUDIT e registra os dados relevantes na tabela de auditoria CHASSI_BOLETIM_AUDIT. Isso inclui o ID de auditoria, IDs de chassi e boletim, status anterior e novo, além do responsável pela modificação, armazenado na coluna MODIFICADO_POR. Essa abordagem proporciona um histórico detalhado das alterações de status na tabela principal, contribuindo para a transparência e rastreabilidade das modificações realizadas no sistema.


    ```SQL
    CREATE OR REPLACE TRIGGER TRG_AUDIT_CHASSI_BOLETIM
    AFTER UPDATE OF STATUS ON CHASSI_BOLETIM
    FOR EACH ROW
    DECLARE
    V_ID_AUDITORIA INTEGER;
    BEGIN
    -- Gerar um novo ID de auditoria
    SELECT SEQ_CHASSI_BOLETIM_AUDIT.NEXTVAL INTO V_ID_AUDITORIA FROM DUAL;

    -- Inserir os dados na tabela de auditoria
    INSERT INTO CHASSI_BOLETIM_AUDIT (ID_AUDITORIA, ID_CHASSI, ID_BOLETIM, STATUS_ANTERIOR, STATUS_NOVO, modificado_por)
    VALUES (V_ID_AUDITORIA, :OLD.ID_CHASSI, :OLD.ID_BOLETIM, :OLD.STATUS, :NEW.STATUS, :NEW.MODIFICADO_POR);
    END;
    /
    ```


</details>


<details>
<br>
<summary><b>Views</b></summary>

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
  <summary><b>Configuração de conexão com Autonomous database</b></summary>
     <br>
  <ul>
    <li>Criação da wallet de conexão</li>
    <li>Liberação de consultas REST</li>
  </ul>
 </details>
 <details>
  <summary><b>Criação de funções e procedures com PL/SQL</b></summary>
     <br>
  <ul>
    <li>Estrutura de uma função</li>
    <li>Estrutura de uma procedure</li>
    <Li>Como executar funções e procedures</Li>
  </ul>
 </details>

  <details>
  <summary><b>Uso de triggers</b></summary>
     <br>
  <ul>
    <li>Estrutura de uma trigger</li>
    <li>Utilização e vantagens</li>
  </ul>
 </details>

   <details>
  <summary><b>Uso de views</b></summary>
     <br>
  <ul>
    <li>Estrutura de uma view</li>
    <li>Utilização e vantagens</li>
    <Li>View hierarquica no oracle</Li>
  </ul>
 </details>

<hr>




 
 
 
 
 
 



