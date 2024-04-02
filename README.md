# Aula 6
## Criando um Banco de Dados

É necessário ter o XAMPP, e dar START no APACHE e MYSQL.
Após iniciar o MYSQL e o APACHE, clique em ADMIN do MYSQL.

Para criar um banco de dados, utilizaremos o seguinte link: http://localhost/phpmyadmin/index.php?

Com a seguinte conexão:
utf8_general_ci
image.png

## Exercício | Banco de Dados
- Insira no banco de dados, dados de 10 alunos; (INSERT)
- Faça uma consulta que traga todos os alunos que têm a sílaba "ma"; (SELECT)
- Faça uma alteração e coloque senha padrão para todos alunos como sendo 123; (UPDATE)
- Remove do banco de dados todos alunos que fazem curso de enfermagem. (DELETE)

### Respostas
1)
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Marcelo', 'TADS', '123');
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Marcio', 'TADS', '123');
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Akin', 'Enfermagem', '123');
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Leonardo', 'TADS', '123');
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Vitor', 'Enfermagem', '123');
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Mauricio', 'TADS', '123');
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Maria', 'TADS', '123');
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Sergio', 'Enfermagem', '123');
INSERT INTO aluno(ra, nome, curso, senha) VALUES ('', 'Leandro', 'Ciência da Computação', '123');

2)
SELECT * FROM aluno WHERE nome LIKE "%ma%";
LIKE só funciona para TEXTO, se for número utilizaremos o seguinte:
WHERE ra = '7';

"%a%"
Isso mostrará qualquer texto que possua o conteúdo "a"
"a%"
Este mostrará um texto que começa com "a"
"%a"
Já isso mostrará todo o texto acabe com o conteúdo "a"
"leonardo%"
Já isso mostrará todo o texto que comece com "leonardo"

3)
UPDATE aluno SET senha = '12345';

4)
DELETE FROM aluno WHERE curso = "Enfermagem";

EXTRA)
Mudar a senha de um aluno chamado 'Gustavo' para 'senhalegal':
UPDATE aluno SET senha = 'senhalegal' WHERE nome = 'Gustavo';

EXTRA²)
Mudar a senha de um aluno que começo com o nome "ma":
UPDATE aluno SET senha = '123' WHERE nome LIKE "ma%";

---

O seguinte código irá mostrar quantas vezes cada grupo aparece em uma tabela:
select curso, count(curso) from aluno group by curso

Para deletar uma tabela inteira:
DELETE FROM aluno;

---
