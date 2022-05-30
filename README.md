# momento-funcionarios

#1 - Inclua suas próprias informações no departamento de tecnologia da empresa
INSERT INTO funcionarios (primeiro_nome, sobrenome, email, telefone, dataContratacao, ocupacao_id, salario, departamento_id) 
VALUES ('Camily', 'Vitória', 'camilyndinha@au.org', '12897364537', '2019-02-08', 
(SELECT ocupacao_id FROM ocupacoes WHERE ocupacao_title LIKE '%Desenvolvedor Web%'), 3500.00, 
(SELECT departamento_id FROM departamento WHERE departamento_name LIKE '%Tecnologia%'));

#2 - A administração está sem funcionários. Inclua os outros elementos do seu grupo do demoday no departamento de administração
INSERT INTO funcionarios (primeiro_nome, sobrenome, email, telefone, dataContratacao, ocupacao_id, salario, departamento_id) 
VALUES ('Diego', 'Santos', 'DiegoGrau@vrumvrum.org', '5567843516', '2021-05-06', 
(SELECT ocupacao_id FROM ocupacoes WHERE ocupacao_title LIKE '%Assistente Administrativo%'), 3000.00, 
(SELECT departamento_id FROM departamento WHERE departamento_name LIKE '%Administração%'));
INSERT INTO funcionarios (primeiro_nome, sobrenome, email, telefone, dataContratacao, ocupacao_id, salario, departamento_id) 
VALUES ('Pedro', 'Henrique', 'Pedrozapzap@games.org', '11872365437', '2020-01-09', 
(SELECT ocupacao_id FROM ocupacoes WHERE ocupacao_title LIKE '%Assistente Administrativo%'), 4000.00, 
(SELECT departamento_id FROM departamento WHERE departamento_name LIKE '%Administração%'));
INSERT INTO funcionarios (primeiro_nome, sobrenome, email, telefone, dataContratacao, ocupacao_id, salario, departamento_id) 
VALUES ('Giullia', 'Maria', 'giugiu@artes.org', '11876354789', '2022-04-07', 
(SELECT ocupacao_id FROM ocupacoes WHERE ocupacao_title LIKE '%Assistente Administrativo%'), 5000.00, 
(SELECT departamento_id FROM departamento WHERE departamento_name LIKE '%Administração%'));

#3 - Agora diga, quantos funcionários temos ao total na empresa?
44
select count(*) from funcionarios

#4 - Quantos funcionários temos no departamento de finanças?
6
SELECT COUNT(funcionarios.primeiro_nome) FROM funcionarios INNER JOIN departamento WHERE departamento.departamento_name LIKE '%Finanças%' AND departamento.departamento_id = funcionarios.departamento_id

#5 - Qual a média salarial do departamento de tecnologia?
5383.33
SELECT ROUND(AVG(funcionarios.salario),2) FROM funcionarios INNER JOIN departamento WHERE departamento.departamento_name LIKE '%Tecnologia%' AND funcionarios.departamento_id = departamento.departamento_id;

#6 - Quanto o departamento de Transportes gasta em salários?
41200.00
SELECT SUM(funcionarios.salario) FROM departamento INNER JOIN funcionarios WHERE departamento.departamento_name LIKE '%Transporte%' AND funcionarios.departamento_id = departamento.departamento_id;

#7 - Um novo departamento foi criado. O departamento de inovações. Ele será locado no Brasil. Por favor, adicione-o no banco de dados

#8 - Novos Funcionários!
Três novos funcionários foram contratados para o departamento de inovações. Por favor, adicione-os: William Ferreira, casado com Inara Ferreira, possui um filho chamado Gabriel que tem 4 anos e adora brincar com cachorros. Ele será programador.Já a Fernanda Lima, que é casada com o Rodrigo, não possui filhos. Ela vai ocupar a posição de desenvolvedora.  Por último, a Gerente do departamento será Fabiana Raulino. Casada, duas filhas (Maya e Laura). 
O salário de todos eles será a média salarial dos departamentos de administração e finanças. 

#9 - Informe todas as regiões em que a empresa atua acompanhadas de seus países

#Filho de quem?

#10 - Joe Sciarra é filho de quem?
Ismael Sciarra
SELECT funcionarios.primeiro_nome, funcionarios.sobrenome FROM dependentes INNER JOIN funcionarios WHERE dependentes.funcionario_id = funcionarios.funcionario_id AND dependentes.primeiro_nome LIKE '%Joe%' AND dependentes.sobrenome LIKE '%Sciarra%'

#11 - Jose Manuel possui filhos?
não
SELECT funcionarios.primeiro_nome, dependentes.primeiro_nome FROM dependentes INNER JOIN funcionarios WHERE dependentes.funcionario_id = funcionarios.funcionario_id AND dependentes.sobrenome LIKE '%Manuel%'

#12 - Qual região possui mais países?

#13 - Exiba o nome cada funcionário acompanhado de seus dependentes
SELECT funcionarios.primeiro_nome, dependentes.primeiro_nome FROM funcionarios INNER JOIN dependentes WHERE funcionarios.funcionario_id = dependentes.funcionario_id

#14 - Karen Partners possui um cônjuge?
Alec
SELECT dependentes.primeiro_nome, dependentes.sobrenome FROM dependentes INNER JOIN funcionarios WHERE funcionarios.funcionario_id = dependentes.funcionario_id AND dependentes.funcionario_id = (SELECT funcionario_id FROM funcionarios WHERE primeiro_nome LIKE '%Karen%' AND sobrenome LIKE '%Partners%');

#15 - O ID da tabela de países não segue um padrão numérico. Na sua visão, qual o impacto disso no desenvolvimento do banco?
nenhum
-

#16 - Escolha um país para se mudar. Qual seria esse país? Por que escolheria esse país? E o departamento. O que seria? Como seriam seus funcionários?

#17 - Atualize as informações na tabela para que seu departamento seja criado.






