# Nomeados ao Oscar

Contém a base de indicados ao Oscar em formato JSON para treinar comandos de consulta no MongoDB. 

* Quantas vezes Natalie Portman foi indicada ao Oscar?

R: 3 vezes

Q:
```sql
SELECT COUNT(*) FROM indicados WHERE "Name" Like "%Natalie Portman%";
```

#

* Quantos Oscars Natalie Portman ganhou?

R: 1 vez

Q:
```sql
select * from indicados_ao_oscar where nome_do_indicado like "%Natalie Portman%" and vencedor = "true";
```

#

* Amy Adams já ganhou algum Oscar?

R: Amy Adams nunca ganhou um Oscar

Q:
```sql
select * from indicados_ao_oscar where nome_do_indicado like "%Amy Adams%" and vencedor = "true";
```

#

* A série de filmes Toy Story ganhou um Oscar em quais anos?

R: ganhou 3 vezes. dois em 2010 e um no ano de 2019

Q:
```sql
select * from indicados_ao_oscar where nome_do_filme like "%Toy Story%" and vencedor = "true";
```

#

* A partir de que ano que a categoria "Actress" deixa de existir? 

R: A partir do ano de 1977

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE categoria = "ACTRESS" ORDER BY ano_cerimonia DESC;
```

#

* Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?

R: Janet Gaynor ganhou o primeiro Oscar para melhor atriz no ano de 1928.

Q:
```sql
select * from indicados_ao_oscar where vencedor = "true" and categoria = "ACTRESS";
```

#

* Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.

R:

Q:
```sql
update indicados_ao_oscar set vencedor = "1" where vencedor = "true";
update indicados_ao_oscar set vencedor = "0" where vencedor = "false";
```

#

* Em qual edição do Oscar "Crash" concorreu ao Oscar?

R: Crash concorreu na 78° Edição

Q:
```sql
SELECT nome_do_filme, cerimonia FROM indicados_ao_oscar WHERE nome_do_filme like "%Crash";
```

#

* O filme Central do Brasil aparece no Oscar?

R: Sim, no ano de 1998

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE nome_do_filme like "Central%";
```

#

* Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. 

R:

Q:
```sql
INSERT INTO indicados_ao_oscar(ano_filmagem,ano_cerimonia,cerimonia,categoria,nome_do_indicado,nome_do_filme,vencedor) VALUES (2016,2017,3,'Melhor Filme de Animação','Laika','Kubo e as Cordas Mágicas','false');
INSERT INTO indicados_ao_oscar(ano_filmagem,ano_cerimonia,cerimonia,categoria,nome_do_indicado,nome_do_filme,vencedor) VALUES (2017,2018,3,'Melhor Filme de Animação','Pixar Animation Studios','Coco','true');
INSERT INTO indicados_ao_oscar(ano_filmagem,ano_cerimonia,cerimonia,categoria,nome_do_indicado,nome_do_filme,vencedor) VALUES (2020,2021,3,'Melhor Filme de Animação','Wolfwalkers','Wolfwalkers','false');
```

#

* Denzel Washington já ganhou algum Oscar?

R: Sim, ja ganhou 2 Oscar. O primeiro oscar no ano de 1990 e o segundo foi em 2002

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE nome_do_indicado like "%Denzel Washington%" AND vencedor = "1";
```

#

* Quais os filmes que ganharam o Oscar de Melhor Filme?

R: Lawrence of Arabia Tom Jones | My Fair Lady | The Sound of Music | A Man for All Seasons | In the Heat of the Night | Oliver! | Midnight Cowboy | Patton | The French Connection | The Godfather | The Sting | The Godfather Part II | One Flew over the Cuckoo's Nest | Rocky | Annie Hall | The Deer Hunter | Kramer vs. Kramer | Ordinary People | Chariots of Fire | Gandhi | Terms of Endearment | Amadeus | Out of Africa | Platoon | The Last Emperor | Rain Man | Driving Miss Daisy | Dances With Wolves | The Silence of the Lambs | Unforgiven | Schindler's List | Forrest Gump | Braveheart | The English Patient | Titanic | Shakespeare in Love | American Beauty | Gladiator | A Beautiful Mind | Chicago | The Lord of the Rings: The Return of the King | Million Dollar Baby | Crash | The Departed | No Country for Old Men | Slumdog Millionaire | The Hurt Locker | The King's Speech | The Artist | Argo | 12 Years a Slave | Birdman or (The Unexpected Virtue of Ignorance) | Spotlight | Moonlight | The Shape of Water | Green Book | Parasite | Nomadland | CODA | Everything Everywhere All at Once | Oppenheimer

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE categoria = "BEST PICTURE" AND vencedor = "1";
```

#


* Bonus: Quais os filmes que ganharam o Oscar de Melhor Filme e Melhor Diretor na mesma cerimonia?

R: Nenhum filme ganhou as duas categorias juntas

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE vencedor = "1" AND categoria = "BEST PICTURE" AND categoria = "DIRECTING";
```

#


* Bonus: Denzel Washington e Jamie Foxx já concorreram ao Oscar no mesmo ano?

R: Não, Eles nunca concorreram o Oscar no mesmo ano

Q:
```sql
SELECT nome_do_indicado, ano_cerimonia FROM indicados_ao_oscar WHERE nome_do_indicado like "%Denzel Washington%" AND nome_do_indicado like "%Jamie Foxx%";
```

#

