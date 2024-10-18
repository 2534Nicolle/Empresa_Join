CREATE DATABASE empresa_join;

CREATE TABLE departamento (
id INT auto_increment primary key not null,
nome VARCHAR(255) not null
);

INSERT INTO departamento (nome)
     values ("Medicina"),
            ("Engenharia"),
            ("Analista de dados"),
            ("Professor"),
            ("Programador");


CREATE TABLE funcionario (
id INT auto_increment primary key not null,
salario DECIMAL(10,2)not null,
nome VARCHAR(100) not null,
id_depar int,
foreign key (id_depar) references departamento(id)
);

INSERT INTO funcionario (salario, nome, id_depar)
     values (1000.00,"Caio",5),
            (4000.00,"Julio",2),
            (4000.00,"Rudrian",4),
            (4500.00,"Fellipe",3),
            (6000.00,"Nicolle",1);

CREATE TABLE dependente (
id INT auto_increment primary key not null,
nome VARCHAR(100),
id_func int,
foreign key (id_func) references funcionario(id)
);

INSERT INTO dependente (nome,id_func)
     values ("Charizard",4),
            ("Pikachu",2),
            ("Gengar",1),
            ("Gyarados",3),
            ("Lugia",5);

-- Exercício 1
SELECT func.nome, 
    (SELECT COUNT(*) 
     FROM depen  
     WHERE depen .id_func = func.id) AS quantidade_dependente
FROM func 
WHERE (SELECT COUNT(*) 
       FROM depen   
       WHERE depen.id_func = func.id) > 2;
       
-- Exercício 2
SELECT departamento.nome AS departamento, funcionario.nome AS funcionario
FROM departamento
LEFT JOIN funcionario 
ON departamento.id = funcionario.id_depar
ORDER BY departamento.nome, funcionario.nome;

-- Exercício 3
SELECT funcionario.nome, dependente.nome AS nome_dependente
FROM funcionario 
LEFT JOIN dependente  
ON funcionario.id = dependente.id_func;

-- Exercício 4
SELECT d.nome AS nome_departamento, 
    (SELECT AVG(f.salario) 
     FROM funcionario f 
     WHERE f.id_depar = d.id) AS media_salarial
FROM departamento d;

-- Exercício 5
SELECT d.nome AS nome_departamento, 
    COUNT(de.id) AS quantidade_dependentes
FROM departamento d
LEFT JOIN funcionario f 
ON d.id = f.id_depar
LEFT JOIN dependente de 
ON f.id = de.id_func
GROUP BY d.nome;

-- Exercício 6
select sum(funcionario.salario) as total_salario
from funcionario;

-- Exercício 7
SELECT d.nome AS nome_departamento, SUM(f.salario) AS custo_total
FROM departamento d
LEFT JOIN funcionario f 
ON d.id = f.id_depar
GROUP BY d.nome;

