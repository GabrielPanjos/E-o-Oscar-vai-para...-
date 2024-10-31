# Nomeados ao Oscar

Contém a base de indicados ao Oscar em formato JSON para treinar comandos de consulta no MongoDB. 

* Quantas vezes Natalie Portman foi indicada ao Oscar?

R: 3 vezes

Q:
```sql
SELECT COUNT(*) FROM indicados WHERE "Name" Like "%Natalie Portman%";
```

* Quantos Oscars Natalie Portman ganhou?

R: 1 vez

Q:
```sql
select * from indicados_ao_oscar where nome_do_indicado like "%Natalie Portman%" and vencedor = "true";
```

* Amy Adams já ganhou algum Oscar?

R: Amy Adams nunca ganhou um Oscar

Q:
```sql
select * from indicados_ao_oscar where nome_do_indicado like "%Amy Adams%" and vencedor = "true";
```

* A série de filmes Toy Story ganhou um Oscar em quais anos?

R: ganhou 3 vezes. dois em 2010 e um no ano de 2019

Q:
```sql
select * from indicados_ao_oscar where nome_do_filme like "%Toy Story%" and vencedor = "true";
```

* A partir de que ano que a categoria "Actress" deixa de existir? 

R: A partir do ano de 1977

Q:
```sql
SELECT * FROM indicados_ao_oscar WHERE categoria = "ACTRESS" ORDER BY ano_cerimonia DESC;
```

* Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?

R: Janet Gaynor ganhou o primeiro Oscar para melhor atriz no ano de 1928.

Q:
```sql
select * from indicados_ao_oscar where vencedor = "true" and categoria = "ACTRESS";
```

* Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.

R:

Q:
```sql
update indicados_ao_oscar set vencedor = "1" where vencedor = "true";
update indicados_ao_oscar set vencedor = "0" where vencedor = "false";
```

* Em qual edição do Oscar "Crash" concorreu ao Oscar?

R: Crash concorreu na 78° Edição

Q:
```sql
SELECT nome_do_filme, cerimonia FROM indicados_ao_oscar WHERE nome_do_filme like "%Crash";
```

* O filme Central do Brasil aparece no Oscar?

R:

Q:
```sql
SELECT nome_do_filme, cerimonia FROM indicados_ao_oscar WHERE nome_do_filme like "%Crash";
```

* Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. 

R:

Q:
```sql

```

* Denzel Washington já ganhou algum Oscar?

R:

Q:
```sql

```


* Quais os filmes que ganharam o Oscar de Melhor Filme?

R:

Q:
```sql

```


* Bonus: Quais os filmes que ganharam o Oscar de Melhor Filme e Melhor Diretor na mesma cerimonia?

R:

Q:
```sql

```


* Bonus: Denzel Washington e Jamie Foxx já concorreram ao Oscar no mesmo ano?

R:

Q:
```sql

```

