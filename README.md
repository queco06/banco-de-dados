use BD170225433;
CREATE TABLE funcionarios (id INT AUTO_INCREMENT PRIMARY KEY,nome VARCHAR(100) NOT NULL,cargo VARCHAR(50) NOT NULL,salario DECIMAL(10,2) NOT NULL);
ALTER TABLE funcionarios ADD COLUMN data_admissao DATE NOT NULL;
ALTER TABLE funcionarios DROP COLUMN cargo;
alter table funcionarios MODIFY COLUMN SALARIO DECIMAL(12,2) NOT NULL;
CREATE TABLE departamentos  (id int auto_increment PRIMARY KEY, nome VARCHAR(100) NOT NULL);
ALTER TABLE funcionarios ADD COLUMN departamento_id INT;
ALTER TABLE funcionarios ADD FOREIGN KEY (departamento_id) REFERENCES departamentos(id);
ALTER TABLE departamentos ADD COLUMN orcamento DECIMAL(12,2);
ALTER TABLE departamentos DROP COLUMN orcamento;
ALTER TABLE departamentos MODIFY COLUMN nome VARCHAR(150) NOT NULL;
ALTER TABLE departamentos RENAME TO setores;
drop table setores;
show tables;
ALTER TABLE funcionarios add column status VARCHAR(20) NOT NULL DEFAULT 'Ativo';
