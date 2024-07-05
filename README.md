# Momento & Seus Funcionários
missão momento, instituto PROA


O que vamos fazer?

# Inclua suas próprias informações no departamento de tecnologia da empresa

INSERT INTO funcionarios(funcionario_id,primeiro_nome,sobrenome,email,senha,telefone,data_contratacao,cargo_id,salario,gerente_id,departamento_id) 
VALUES (208,'Kayky','Kayky Teixeira','Kaykyteixeira@proa','123456','11987492156','2024-07-05',9,24000.00,NULL,13);

# Agora diga, quantos funcionários temos ao total na empresa?

SELECT COUNT(*) from momento.funcionarios;

# Quantos funcionários temos no departamento de finanças?

SELECT COUNT(*) from momento.funcionarios WHERE departamento_id = 10;

# Qual a média salarial do departamento de tecnologia?

SELECT SUM(salario) FROM funcionarios WHERE departamento_id = 5;

# Um novo departamento foi criado. O departamento de inovações. Ele será locado no Brasil. Por favor, adicione-o no banco de dados.

INSERT INTO departamentos (departamento_id, departamento_nome, escritorio_id)
VALUES (14, 'Inovações',  (SELECT escritorio_id FROM escritorios WHERE pais_id = 'BR'));

# Três novos funcionários foram contratados para o departamento de inovações. Por favor, adicione-os: William Ferreira, casado com Inara Ferreira, possuem uma filha chamada Maria Antônia que tem 1 anos e adora brincar com cachorros. Ele será programador. Já a Fernanda Lima, que é casada com o Rodrigo, não possui filhos. Ela vai ocupar a posição de desenvolvedora. Por último, a Gerente do departamento será Sumaia Azevedo. Casada, duas filhas (Tainã e Nathalia).

![image](https://github.com/teixeirackayky29/Miss-oMomento_BD/assets/95193248/ae5811d5-8863-48a2-9398-2f20bbbfa552)

# Informe todas as regiões em que a empresa atua acompanhadas de seus países.

![image](https://github.com/teixeirackayky29/Miss-oMomento_BD/assets/95193248/0a875b0b-a7e2-4730-8305-e18158bab5b6)

# Joe Sciarra é filho de quem?

SELECT * FROM dependentes d INNER JOIN funcionarios f ON d.funcionario_id = f.funcionario_id WHERE d.primeiro_nome = 'Joe' AND d.sobrenome = 'Sciarra';

# Jose Manuel possui filhos?

SELECT * FROM dependentes d INNER JOIN funcionarios f ON d.funcionario_id = f.funcionario_id WHERE f.primeiro_nome = 'Jose Manuel';

# Qual região possui mais países?

![image](https://github.com/teixeirackayky29/Miss-oMomento_BD/assets/95193248/52527ae8-0bbc-469e-abf6-5e1501de0bd4)

# Exiba o nome cada funcionário acompanhado de seus dependentes.

SELECT f.primeiro_nome AS nome_responsavel, f.sobrenome AS sobrenome_responsavel, d.primeiro_nome AS nome_dependente, d.sobrenome AS sobrenome_dependente, d.relacionamento
FROM funcionarios f
INNER JOIN dependentes d ON f.funcionario_id = d.funcionario_id;

#Karen Partners possui um(a) cônjuge?

SELECT * FROM dependentes d INNER JOIN funcionarios f ON d.funcionario_id = f.funcionario_id WHERE d.relacionamento = 'Cônjuge' AND f.primeiro_nome = "Karen" AND f.sobrenome = "Partners";



