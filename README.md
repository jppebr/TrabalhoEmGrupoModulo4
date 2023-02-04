Trabalho Em Grupo Modulo 4

Nesse  projeto, nossa equipe  precisava montar um dashboard com  base no conjunto de dados que escolhemos dentro dos que nos foram disponibilizados, e  escolhemos o tema de Game of Thrones. 
https://drive.google.com/drive/folders/1vWOXld-1rxQsFj0_QhtEpaAvD0Fbwefx (Conjunto de dados brutos)

Para isso, elaboramos ao todo  4 perguntas em cima desse conjunto de dados brutos, o que nos guiou para criar os relacionamentos no banco de dados, sendo elas:






1. Quais personagens da série têm mais tempo de tela?
![Gráfico-personagens](https://user-images.githubusercontent.com/114230642/216784839-c6c562f2-a96c-43ce-847a-392f09c9b109.png)

v1-
SELECT characters, House_name
FROM got_characters INNER JOIN got_houses ON got_characters.house_id = got_houses.house_id ORDER BY characters;

v2-
SELECT characters, House_name, Episodes_appeared
FROM got_characters INNER JOIN got_houses ON got_characters.house_id = got_houses.house_id ORDER BY Episodes_appeared;

v3-
SELECT characters, House_name,Time_screen
FROM got_characters INNER JOIN got_houses ON got_characters.house_id = got_houses.house_id  
ORDER BY `got_characters`.`Time_screen` DESC









2. Quais foram os episódios com as melhores avaliaçõe?
![Gráfico-Episódios](https://user-images.githubusercontent.com/114230642/216784858-6a566767-d789-44cd-b61b-d7b0cecfcd62.png)

v1-
SELECT Season, episode, Rating, Votes FROM got_episodes_v4 
where Rating = '9,9';










3. Quais regiões tem mais casas? 

![Gráfico-Regiões](https://user-images.githubusercontent.com/114230642/216784873-e62c4d4d-431d-4ca2-aceb-dbc4881be3e0.png)
v1-
select 
House_name,
count(*) as qtd,Region
from got_houses group by House_name  
ORDER BY `Region`;


v2-
SELECT house_name from got_houses WHERE Region = 'Crownlands';

v3-
SELECT region,count(house_name) from got_houses GROUP by Region  
ORDER BY `region` ASC



4. Qual a quantidade de episodio por diretores?
![Gráfico-Diretores](https://user-images.githubusercontent.com/114230642/216784891-3a69ad2c-6842-4e02-98e8-f5e3dc55e92f.png)

v1-SELECT Director, COUNT(Episode) FROM got_episodes_v4 GROUP by Director;
