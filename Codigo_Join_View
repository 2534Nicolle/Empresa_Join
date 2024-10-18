create database ger_join_1e;

create table funcionarios (
cod int auto_increment primary key,
nome varchar(255),
especialidade varchar(255)
);
insert into funcionarios (nome, especialidade)
    values("José", "Engenheiro"),
          ("João", "Mestre de obras"),
          ("Maria", "Contabilista");
         
create table dependentes (
cod int auto_increment primary key ,
nome varchar(255) ,
cod_func int,
foreign key (cod_func) references funcionarios(cod)
);

insert into dependentes (nome, cod_func)
    values("Pedro", 1),
          ("Alices", 1),
          ("Luana", 3);
          
Select*from dependentes; 

select funcionarios.nome, dependentes.nome 
from funcionarios
inner join dependentes
on funcionarios.cod = dependentes.cod_func
where funcionarios.cod = 1;

select funcionarios.nome, dependentes.nome 
from funcionarios
left join dependentes
on funcionarios.cod = dependentes.cod_func
where dependentes.nome is null;

select funcionarios.nome, dependentes.nome 
from funcionarios
right join dependentes
on funcionarios.cod = dependentes.cod_func
where funcionarios.cod is null;

-----------------------------------------------------

CREATE view VW_LISTA_FUNCIONARIOS AS
SELECT NOME, ESPECIALIDADE
FROM funcionarios;

SELECT * FROM VW_LISTA_FUNCIONARIOS;

CREATE VIEW VW_LISTA_DEPENDENTES AS
SELECT NOME
FROM dependentes;

SELECT * FROM VW_LISTA_DEPENDENTES;

CREATE VIEW VW_FUNCIONARIO_COM_DEPENDENTES AS
SELECT funcionarios.NOME AS Funcionario_Nome, dependentes.NOME AS Dependente_nome
FROM funcionarios
INNER JOIN dependentes 
ON funcionarios.cod = dependentes.cod_func;

SELECT * FROM VW_FUNCIONARIO_COM_DEPENDENTES;

CREATE VIEW VW_FUNCIONARIO_COM_DEPENDENTES_LEFT AS
SELECT funcionarios.NOME AS Funcionario_Nome, dependentes.NOME AS Dependente_Nome
FROM funcionarios
LEFT JOIN dependentes 
ON funcionarios.cod = dependentes.cod_func;

SELECT * FROM VW_FUNCIONARIO_COM_DEPENDENTES_LEFT;

CREATE VIEW VW_DEPENDENTE_COM_FUNCIONARIOS_RIGHT AS
SELECT funcionarios.NOME AS Funcionario_Nome, dependentes.NOME AS Dependente_Nome
FROM funcionarios
RIGHT JOIN dependentes 
ON funcionarios.cod = dependentes.cod_func;

SELECT * FROM VW_DEPENDENTE_COM_FUNCIONARIOS_RIGHT;

CREATE VIEW VW_FUNCIONARIO_COM_DEPENDENTES_LEFT_EXCLUDING AS
SELECT funcionarios.NOME AS Funcionario_Nome, dependentes.NOME AS Dependente_Nome
FROM funcionarios
LEFT JOIN dependentes 
ON funcionarios.cod = dependentes.cod_func
WHERE funcionarios.cod is null;

SELECT * FROM VW_FUNCIONARIO_COM_DEPENDENTES_LEFT_EXCLUDING;

CREATE VIEW VW_DEPENDENTE_COM_FUNCIONARIOS_RIGHT_EXCLUDING AS
SELECT funcionarios.NOME AS Funcionario_Nome, dependentes.NOME AS Dependente_Nome
FROM funcionarios
RIGHT JOIN dependentes 
ON funcionarios.cod = dependentes.cod_func
WHERE funcionarios.cod is null;

SELECT * FROM VW_DEPENDENTE_COM_FUNCIONARIOS_RIGHT_EXCLUDING;

