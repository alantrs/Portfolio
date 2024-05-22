### Alan Araujo Rodrigues

### Introdução

  Meu nome é Alan Araujo Rodrigues, tenho 28 anos e estou cursando o 6° semestre de Banco de Dados. Ingressei na Fatec no segundo semestre de 2021, onde obtive meu primeiro contato com a programação.

  Durante a minha formação adquiri diversos conhecimentos sobre tecnologias, metodologias, ferramentas e boas práticas de desenvolvimento de software. Com a Aprendizagem por Projetos Integrados (API), tive a oportunidade de colocar em prática os conteúdos estudados em sala de aula e elaborar soluções para problemas reais do mercado de trabalho, tendo como clientes empresas parceiras da faculdade.

  Atualmente sou Desenvolvedor de Software na empresa Datainfo, atuando com tecnologias como Java, Javascript e Postgresql. 

<p align="center">
  <img src="https://github.com/alantrs/Portfolio/blob/5e81cae07a03937c77bcf30c22e610de916aa445/imagem/WhatsApp%20Image%202024-04-05%20at%2011.03.14%20AM.jpeg" width="203" height="250"></a>
</p>

## Contatos

 <a href="https://www.linkedin.com/in/alanaraujo1995/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
 <a href="https://github.com/alantrs" target="_blank"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" target="_blank"></a>
 <br>

## Meus Principais Conhecimentos

- Java: Para criação de API's REST com Spring.
- SQL: Para modelagem, criação e manipulação de Banco de Dados.
- Banco de dados: Gerenciamento e administração de Oracle e PostgreSQL.

# Projeto 1: 2021-2

### Empresa parceira  

<p align="center">
    <b>Interno - <a href="https://fatecsjc-prd.azurewebsites.net/">Fatec</a></b> 
    <img src="https://github.com/alantrs/Bertoti/blob/fb16a234423d629719a0fa98c0c15c1295ef0420/metodologia/Imagens/Carcara.png" alt="Logo carcara analises">
</p>

## Descrição do projeto

O desafio proposto foi criar um projeto que tem como objetivo analisar os dados oficiais da COVID-19 no Estado de São Paulo e entregá-los ao usuário de forma clara e contextualizada, através de visualizações gráficas ou não-gráficas.

A solução desenvolvida foi um sistema web em Python utilizando Flask, o qual processava os dados estatísticos da COVID disponibilizados pelo governo em arquivos CSV. Esse sistema permitia aos usuários visualizarem gráficos informativos, incluindo barras e setores, com estatísticas detalhadas sobre o vírus. Além disso, apresentava insights relevantes derivados dos dados existentes por meio de cálculos integrados.

[GIT](https://github.com/SoSoJigsaw/Carcara)

## Tecnologias utilizadas

- **Python**: linguagem de programação para o desenvolvimento back-end.
- **Flask**: Flask, um framework web em Python, foi incorporado para facilitar a criação de aplicativos web.
- **Pandas**: O Pandas foi empregado para realizar a leitura e manipulação dos dados provenientes de arquivos CSV.
- **Html, Css**: A combinação destas linguagens permitiu criarmos a parte visual do nosso projeto.

## Contribuições pessoais

Por ser o primeiro projeto, dediquei meu tempo aos estudos e trabalhar em conjunto com o time de desenvolvimento da equipe, atuando principalmente no backend utilizando python para tratar os dados e criar endpoints para acesso a eles. Atuei na construção de métodos para expor os dados de maneira clara e organizada.
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

Nesse projeto aprendi a introdução aos algoritmos com Python e noções de versionamento de código com git. Também aprendi a introdução de metodologias ágeis no desenvolvimento de software.
<br>
### Hard Skills

<details>
<summary><b>Python: sei fazer com autonomia</b></summary>
<br>
<ul>
  <li>Lógica de programação</li>
  <li>Estruturas de controle de fluxo: if else, while loop, for loop</li>
  <li>Manipulação de dados</li>
</ul>
</details>
<details>
<summary><b>Flask: sei fazer com autonomia</b></summary>
<br>
<ul>
  <li>Criação de endpoints</li>
  <li>Métodos HTTP GET e POST</li>
</ul>
</details>

### Soft Skills

<details>
  <summary><b>Comunicação</b></summary>
  <br>
  <ul>
    <li>Durante este semestre, as aulas no formato EAD apresentaram desafios extras na comunicação, o que me motivou a aprimorar ainda mais essa habilidade com meu grupo. Investir na comunicação com a equipe ajudou a fortalecer os laços entre os membros e facilitou o aprendizado por meio das experiências individuais de cada um.</li>
  </ul>
</details>

<details>
  <summary><b>Trabalho em equipe</b></summary>
  <br>
  <ul>
    <li>Ao participar ativamente do desenvolvimento do projeto, pude aprimorar significativamente minhas habilidades de trabalho em equipe, as quais são fundamentais para o sucesso e a realização dos objetivos propostos.</li>
  </ul>
</details>  

<hr>
    
# Projeto 2: 2022-1

### Empresa parceira  

<p align="center">
    <b><a href="https://www.domrock.net/">Dom Rock</a></b>
</br>
    <img src="https://github.com/alantrs/Bertoti/blob/efd7a4e3055f78276feb65f55b0702623e0f2636/metodologia/Imagens/domrock2.png" alt="Logo dom rock">
</p>


## Descrição do projeto

O desafio proposto foi desenvolver uma solução eficaz para o gerenciamento da ativação de clientes na plataforma Dom Rock. A meta era criar um sistema que facilitasse significativamente a entrada de dados dos clientes, possibilitando uma alocação de recursos mais eficiente e precisa na plataforma.

A solução consiste em uma aplicação desktop desenvolvida em Java, projetada para capturar dados personalizados de cada cliente e utilizar essas informações para alocar recursos de forma eficiente na plataforma. Essa abordagem abrange a estimativa de consumo de recursos com base em critérios como o volume de dados do cliente e o número de usuários. Além disso, a solução foi concebida para oferecer funcionalidades adicionais, como a geração de relatórios e consultas, proporcionando uma visão abrangente e detalhada das atividades e necessidades dos clientes.

[GIT](https://github.com/CarcaraTec/Dom-Rock)

## Tecnologias utilizadas

- **Java**: Linguagem para desenvolvimento da aplicaçãoback-end.
- **Java Swing**: Biblioteca de interface gráfica de usuário utilizada para criar interfaces gráficas.
- **PostgreSQL**: Sistema de gerenciamento de banco de dados relacional para gerenciamento dos dados.

## Contribuições pessoais

Fui o administrador do banco de dados da equipe. Desenvolvi a modelagem de dados e a criação da base de dados por completo. Ajudei a equipe de backend sendo solicitado por melhorias na distribuição dos dados promovendo a maior facilidade para manipulação dos mesmos.
<br>
    <details>
<summary><b>Modelagem do banco de dados</b></summary>
<br>

Neste projeto, realizei a modelagem de dados para a nossa base, com o propósito de representar de forma eficaz as informações inseridas pelo cliente e como esses dados serão distribuídos em nosso sistema.

![Modelagem do banco de dados](https://github.com/alantrs/Bertoti/blob/778fd69f6e9fecddd2342af75295ff9542562f1e/metodologia/Imagens/modelagem-domrock.jpeg)
</details>

<details>
<summary><b>Implementação física do banco de dados</b></summary>
<br>

Após validar nossa modelagem, procedi com a implementação física da nossa base de dados. Isso envolveu a tradução do nosso modelo entidade-relacionamento para scripts SQL.

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

Aprendi a base para criar um banco de dados. Como iniciar uma modelagem de dados, definir cardinalidades e transformar o modelo conceitual em script SQL. Aprendi alguns comandos básicos para trabalhar com versionamento de código com Git.

### Hard Skills

<details>
  <summary><b>Recursos básicos de Banco de dados: sei fazer com autonomia</b></summary>
    <br>
  <ul>
    <li>Estrutura do banco, distribuição das tabelas</li>
    <Li>Modelo conceitual, Modelo lógico e Modelo físico</Li>
    <Li>Criar script</Li>
    <Li>Realizar querys simples</Li>
  </ul>
 </details>

 <details>
  <summary><b>Git: sei fazer com autonomia</b></summary>
     <br>
  <ul>
    <li>Comandos básicos: git add, git commit, git pull, git push</li>
    <Li>Criar branches</Li>
  </ul>
 </details>

### Soft Skills

<details>
  <summary><b>Adaptabilidade</b></summary>
  <br>
  <ul>
    <li>Lidar com uma equipe totalmente nova exigiu rápida adaptação e flexibilidade para nos ajustarmos ao ambiente e às dinâmicas de trabalho. A capacidade de ser flexível e adaptável foi essencial para responder de forma eficaz às mudanças e desafios que surgiram, permitindo-nos manter o foco no objetivo final e atender às necessidades do cliente de maneira ágil e eficiente</li>
  </ul>
</details> 
<details>
  <summary><b>Aprendizado contínuo</b></summary>
  <br>
  <ul>
    <li>A partir desse semestre foi introduzido a tecnologia de banco de dados para a aplicação a ser desenvolvida, e foi necessário estudar para aprender sobre SQL e sobre PostgreSQL.</li>
  </ul>
</details> 

<hr>

# Projeto 3: 2022-2

### Empresa parceira  

<p align="center">
    <b>IACIT soluções tecnológicas S.A.</b> 
    <img src="https://github.com/alantrs/Bertoti/blob/ce55d69f624ba22495bcf76f626bb86899750763/metodologia/Imagens/Iacit.png" alt="Logo da IACIT soluções tecnológicas">
</p>


## Descrição do projeto

Foi proposto um desafio para desenvolver um sistema capaz de importar dados meteorológicos de arquivos CSV disponibilizados pela empresa, armazená-los em uma base de dados e gerar relatórios solicitados pelos clientes da empresa IACIT. 

A solução foi criar uma aplicação web capaz de filtrar os registros por regiões, estados, estações, tipo de dado e ranges de datas, além de exibir as informações em formato de gráficos e cards. Por fim, obter relatórios com base na pesquisa realizada.

 [GIT](https://github.com/CarcaraTec/IACIT)
 
 ## Tecnologias utilizadas

- **Java e Spring boot**: A linguagem Java foi utilizada em conjunto ao framework Spring para desenvolvimento web e criação de API's REST.
- **PostgreSQL**: Sistema de gerenciamento de banco de dados relacional para gerenciamento dos dados.
- **Html, Css, Javascript**: Combinação utilizada para criar uma interface amigável e intuitiva para os usuários da aplicação.

## Contribuições pessoais

Fui o administrador do banco de dados da equipe em conjunto com a função de Scrum master. Como DBA desenvolvi desde a modelagem de dados até a criação da base de dados completa. Como scrum master fui responsável por garantir que o processo Scrum estivesse sendo seguido corretamente e que a equipe estivesse funcionando de maneira eficaz e produtiva.
<br>
    <details>
<summary><b>Modelagem do banco de dados</b></summary>
<br>

No caso deste projeto, o objetivo da modelagem de dados foi representar os dados meteorológicos, como temperatura, umidade e outros indicadores. 
<br>

![Modelagem do banco de dados](https://github.com/alantrs/Bertoti/blob/e19d9567debe132ef4387b306ba9451d048716cf/metodologia/Imagens/modelagem_img1.jpeg)
</details>

    
<details>
<summary><b>Implementação física do banco de dados</b></summary>
<br>
Após validar nossa modelagem, procedi com a implementação física da nossa base de dados. Isso envolveu a tradução do nosso modelo entidade-relacionamento para scripts SQL.
    
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
    Backup é um processo essencial para proteger e preservar dados importantes. No nosso projeto foram realizados backups a cada sprint, para garantir a integridade e segurança dos dados. O backup era gerado por esse simples comando.
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

### Hard Skills

<details>
  <summary><b>Recursos de Banco de dados: sei fazer com autonomia</b></summary>
    <br>
  <ul>
    <li>Normalização</li>
    <Li>Relacionamento das tabelas</Li>
    <Li>Constraints</Li>
  </ul>
 </details>
<details>
  <summary><b>SQL: sei fazer com autonomia</b></summary>
    <br>
  <ul>
    <li>DDL (Data Definition Language)</li>
    <li>DML (Data Manipulation Language)</li>
    <li>DCL (Data Control Language)</li>
    <Li>Querys com joins e funções de agrupamento</Li>
  </ul>
 </details>
 <details>
  <summary><b>Administração do PostgreSQL: sei fazer com ajuda</b></summary>
     <br>
  <ul>
    <li>Política de backup</li>
    <li>Criação de usuário</li>
    <Li>Definição de roles</Li>
  </ul>
 </details>

<details>
  <summary><b>Scrum: sei fazer com autonomia</b></summary>
  <ul>
    </br>
    <li>Compreensão dos princípios e papéis do Scrum.</li>
   <li>Remoção de impedimentos</li>
   <li>Comunicação e colaboração</li>
   <li>Feedback e melhoria contínua</li>
   <li>Habilidades de liderança e organização</li>
  </ul>
 </details>

### Soft Skills

<details>
  <summary><b>Organização</b></summary>
  <br>
  <ul>
    <li>Fui responsável por organizar o repositório do projeto, as documentações, e tambem o controle do burndown. Ser organizado foi fundamental para manter tudo alinhado para equipe manter o foco em executar de forma clara.</li>
  </ul>
</details> 

<details>
  <summary><b>Comunicação</b></summary>
  <br>
  <ul>
    <li>
      Atuando como master também fui responsável por garantir uma comunicação eficaz e objetiva com minha equipe, proporcionando clareza e assegurando o cumprimento da metodologia definida para o projeto.
    </li>
  </ul>
</details> 


<hr>

# Projeto 4: 2023-1

### Empresa parceira

<p align="center">
    <b>Embraer</b> 
    <img src="imagem/embraer.png" alt="Logo embraer">
</p>

## Descrição do projeto

O desafio proposto foi desenvolver uma plataforma que permitisse aos usuários consultar os itens instalados nas aeronaves. O sistema deveria incluir funcionalidades de verificação e edição dos itens instalados ou aplicáveis a determinados "chassis" de acordo com uma base de dados fornecida.

A solução foi um sistema que armazenava todas as regras de composição de itens em um banco de dados. Quando um número de chassi era consultado, o sistema recuperava as regras de composição correspondentes desse chassi no banco de dados. Em seguida, os itens compatíveis com o chassi consultado eram exibidos na tela para o usuário.

[GIT](https://github.com/CarcaraTec/Embraer)

## Tecnologias utilizadas

- **Java e Spring boot**: A linguagem Java foi utilizada em conjunto ao framework Spring para desenvolvimento web e criação de API's REST.

- **Vue.js**: Framework javascript Vue.js para o frontend da aplicação.

- **Autonomous Database Oracle**: Solução de gerenciamento de banco de dados em nuvem para gerenciamento dos dados.

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
Uma das minhas contribuições foi desenvolver soluções para tratar a logica de negócio com funcionalidades da linguagem PL/SQL da oracle. 
Essa é uma procedure que tem como objetivo verificar se determinados itens estão instalados de fábrica em uma aeronave. Ela percorre as tabelas chassi e logica_fabrica e, para cada combinação de chassi e item, utiliza a função verificar_instalacao_fabrica para determinar se o item está instalado.
  
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
Essa trigger foi criada para realizar auditoria na tabela CHASSI_BOLETIM após operações de atualização no campo STATUS. Quando uma atualização ocorre, a trigger gera um novo identificador de auditoria utilizando a sequência SEQ_CHASSI_BOLETIM_AUDIT e registra os dados relevantes na tabela de auditoria CHASSI_BOLETIM_AUDIT. Essa abordagem proporciona um histórico detalhado das alterações de status na tabela principal, contribuindo para a transparência e rastreabilidade das modificações realizadas no sistema.


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

Para facilitar a consulta e diminuir a complexidade para o backend, criei essa view para retornar um caminho hierarquico das lógicas, onde é possivel definir uma entrada (buscando a dependencia ou buscando pelo nivel) para recuperar a lógica de aplicação de um determinado item.

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


### Hard Skills

 <details>
  <summary><b>Funções e Procedures com PL/SQL: sei fazer com ajuda</b></summary>
     <br>
  <ul>
    <li>Estrutura e funcionamento de uma função</li>
    <li>Estrutura e funcionamento de uma procedure</li>
    <Li>Como executar funções e procedures</Li>
  </ul>
 </details>

  <details>
  <summary><b>Triggers: sei fazer com autonomia</b></summary>
     <br>
  <ul>
    <li>Estrutura e funcionamento de uma trigger</li>
    <li>Utilização e vantagens</li>
  </ul>
 </details>

   <details>
  <summary><b>Views: sei fazer com autonomia</b></summary>
     <br>
  <ul>
    <li>Estrutura e funcionamento de uma view</li>
    <li>Utilização e vantagens</li>
    <Li>Hierarquia de dados no oracle com connect_by</Li>
  </ul>
 </details>

### Soft Skills

<details>
  <summary><b>Proatividade</b></summary>
  <br>
  <ul>
    <li>Utilizando uma tecnologia nova, o Autonomous Database da Oracle, precisei ser proativo em aprender sobre a ferramenta e descobrir funcionalidades que ajudariam no controle da lógica do projeto. Essa soft skill me permitiu aprender muito e ver minha capacidade de tomar a frente de uma responsabilidade que era fundamental para o funcionamento do projeto.</li>
  </ul>
</details> 

<details>
  <summary><b>Comunicação e Trabalho em equipe</b></summary>
  <br>
  <ul>
  <li>Durante o projeto, contribuí significativamente para o desenvolvimento do time ao compartilhar os conhecimentos que adquiri em ferramentas avançadas de banco de dados. Essa iniciativa permitiu que a equipe melhorasse a arquitetura e o desempenho do backend, otimizando consultas e manipulações de dados. Ao apresentar esses conhecimentos, busquei garantir que todos os membros pudessem aproveitar ao máximo as capacidades da base de dados, promovendo um ambiente de trabalho colaborativo e eficiente. Além disso, estar aberto a compartilhar experiências e aprender com os colegas foi essencial para fortalecer os laços dentro do time e alcançar nossos objetivos de maneira mais eficaz.
  </li>
  </ul>
</details>


<hr>

# Projeto 5: 2023-2

### Empresa parceira
<p align="center">
    <b>Oracle</b> 
    <img src="imagem/projeto_oracle.png" alt="Logo oracle">
</p>

## Descrição do projeto

Criar uma plataforma online abrangente para a gestão eficiente de restaurantes, oferecendo funcionalidades como painéis de controlo, gráficos, relatórios e gestão de pessoal, fornecedores e inventário. O objetivo é ajudar os proprietários de restaurantes a enfrentar desafios como o controlo de custos, a gestão de equipas e o inventário, com vista a melhorar as suas operações.

A solução consistiu em um sistema que consultava todos os dados armazenados na base de dados, realizava cálculos para fornecer diversos insights e disponibilizava-os em gráficos, tabelas e cards intuitivos.

[GIT](https://github.com/CarcaraTec/Cloud-Kitchen-Oracle)

## Tecnologias utilizadas 

- **Java e Spring boot**: A linguagem Java foi utilizada em conjunto ao framework Spring para desenvolvimento web e criação de API's REST.
- **Vue.js**: Utilizamos o framework javascript Vue.js para o frontend da aplicação.
- **Autonomous Database Oracle**: Solução de gerenciamento de banco de dados em nuvem para gerenciamento dos dados.
  
## Contribuições pessoais

Neste projeto, assumi um papel central no desenvolvimento do backend utilizando Java e Spring Boot. Fui encarregado de conceber a arquitetura do projeto e implementar endpoints para fornecer dados tratados ao frontend, facilitando sua exibição em gráficos, tabelas e cards. Além disso, fui responsável pela implementação de testes unitários dentro do fluxo de desenvolvimento DevOps desenvolvido pela equipe.
<br>

<details>
<summary><b>Calculo de permanência média</b></summary>
<br>

Um dos métodos que desenvolvi para insights foi o calculo de permanencia média do cliente no restaurante. No método, são consultadas as comandas registradas no sistema dentro do intervalo de tempo especificado. Para cada comanda encontrada, são calculados os horários de abertura e fechamento, e a duração da permanência do cliente é obtida através da diferença entre esses horários. A duração total de todas as permanências é então somada e dividida pelo número de comandas para obter a média.


  ```java
  public Duration calculoPermaneciaMedia(LocalDateTime dataInicio, LocalDateTime dataFim) {
        List<Comanda> comandas = comandaRepository.findByHorarioAberturaBetween(dataInicio, dataFim);

        Duration duracaoTotal = Duration.ZERO;

        for (Comanda comanda : comandas) {
            Timestamp abertura = comanda.getHorarioAbertura();
            Timestamp fechamento = comanda.getHorarioFechamento();

            LocalDateTime aberturaLocalDateTime = abertura.toInstant().atZone(ZoneId.systemDefault()).toLocalDateTime();
            LocalDateTime fechamentoLocalDateTime = fechamento.toInstant().atZone(ZoneId.systemDefault()).toLocalDateTime();

            Duration duracaoComanda = Duration.between(aberturaLocalDateTime, fechamentoLocalDateTime);

            duracaoTotal = duracaoTotal.plus(duracaoComanda);
        }

        Integer numeroDeComandas = comandas.size();
        if (numeroDeComandas > 0) {
            return duracaoTotal.dividedBy(numeroDeComandas);
        } else {
            return Duration.ZERO;
        }
    }
  ```
</details>


<details>
<summary><b>Rank de pratos vendidos</b></summary>
<br>
Outro método de insight que desenvolvi foi o de ranking de pratos vendidos. Este método tem como objetivo fornecer um ranking dos pratos mais e menos vendidos no restaurante, agrupados por tipo de produto. Utilizando chamadas para outros métodos separados, essa lógica identifica os produtos com as maiores e menores quantidades de vendas.

  ```java

  public ExibicaoProdutosVendidos maisVendidos(){
        List<ExibicaoRankPratoDTO> pratosPrincipaisMaisVendidos = pratosPrincipaisMaisVendidos();
        List<ExibicaoRankPratoDTO> sobremesasMaisVendidos = sobremesasMaisVendidos();
        List<ExibicaoRankPratoDTO> bebidasMaisVendidos = bebidasMaisVendidos();

        return new ExibicaoProdutosVendidos(pratosPrincipaisMaisVendidos, sobremesasMaisVendidos, bebidasMaisVendidos);
    }

    public ExibicaoProdutosVendidos menosVendidos(){
        List<ExibicaoRankPratoDTO> pratosPrincipaisMenosVendidos = pratosPrincipaisMenosVendidos();
        List<ExibicaoRankPratoDTO> sobremesasMenosVendidos = sobremesasMenosVendidos();
        List<ExibicaoRankPratoDTO> bebidasMenosVendidos = bebidasMenosVendidos();

        return new ExibicaoProdutosVendidos(pratosPrincipaisMenosVendidos, sobremesasMenosVendidos, bebidasMenosVendidos);
    }
  ```

</details>

<details>
<summary><b>Testes unitários</b></summary>
<br>
Fiquei responsável pela implementação de testes unitários no backend. Neste teste unitário, confirmamos se o serviço rankVendaProdutoService retorna corretamente o ranking de vendas de produtos em um período específico. 

  ```java
  @BeforeEach
    public void setUp (){
        rankVendaProduto = RankVendaProduto.builder().codPrato(1L)
                .nomePrato("Prato1").diaDaSemana("Domingo").quantidadeTotal(10)
                .valorTotalProduto(new BigDecimal("10"))
                .impactoPorcentagem(new BigDecimal("10")).build();
    }

    @Test
    public void rankVendaProdutosOk(){
        Mockito.when(rankVendaProdutoRepository
                .rankDeVendas(1,"2023-08-01","2023-08-02"))
                .thenReturn(Collections.singletonList(rankVendaProduto));

        List<RankVendaProduto> rankVendaProdutos = rankVendaProdutoService.rankVendaProdutos(1,"2023-08-01","2023-08-02");

        Assertions.assertEquals(Collections.singletonList(rankVendaProduto),rankVendaProdutos);
        Mockito.verify(rankVendaProdutoRepository,Mockito.times(1)).rankDeVendas(1,"2023-08-01","2023-08-02");
    }
  ```

</details>

## Aprendizados efetivos

### Hard Skills

<details>
  <summary><b>Java e Spring Boot</b></summary>
  <br>
  <ul>
    <li></li>
  </ul>
</details> 

<details>
  <summary><b>Devops</b></summary>
  <br>
  <ul>
    <li></li>
  </ul>
</details> 

<details>
  <summary><b>Testes com Junit</b></summary>
  <br>
  <ul>
    <li></li>
  </ul>
</details> 

### Soft Skills

<details>
  <summary><b>Colaboração</b></summary>
  <br>
  <ul>
    <li></li>
  </ul>
</details> 

<details>
  <summary><b>Proatividade</b></summary>
  <br>
  <ul>
    <li></li>
  </ul>
</details> 

<hr>


# Projeto 6: 2024-1

### Empresa parceira

## Descrição do projeto

[GIT](https://github.com/CarcaraTec/Imagem-api6sem)
## Tecnologias utilizadas 

## Contribuições pessoais

## Aprendizados efetivos

### Hard Skills

### Soft Skills


<hr>
