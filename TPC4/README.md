# Título
## Autor: nome, id, foto
## Resumo: lista de parágrafos
## Lista de resultados: links para os ficheiros da resolução

```python
sala1 = ( 120,[],"Lavagante" )
sala2 = (90,[],"Uma Grande, Corajosa e Bela Viagem" )
sala3 = (150,[],"The Conjuring 4: Extrema-Unção" )
sala4 = (100,["A1", "A2", "A3", "A4", "A5", "A6", "A7", "A8", "A9", "A10", "B1", "B2", "B3", "B4", "B5", "B6", "I10", "J1", "J2", "J3", "J4", "J5", "J6", "J7", "J8", "J9", "J10"],"Batalha Atrás de Batalha" )
sala5 = (130,[],"Demon Slayer: Castelo Infinito" )
sala6 = (80,[],"The Smashing Machine: Coração de Lutador" )
cinema = [sala1,sala2,sala3,sala4,sala5,sala6]


#1. `listar( cinema )` - que lista no monitor todos os filmes que estão em exibição nas salas do cinema passado como argumento;

def listar(cinema):
    i = 0
    
    while i <= len(cinema):
     print(f"Sala{i+1}: {cinema[i][2]}")
     i = i + 1

#2. `disponivel( cinema, filme, lugar )` - que dá como resultado **False** se o lugar lugar já estiver ocupado na sala onde o filme está a ser exibido e dará como resultado **True** se o inverso acontecer;

def disponivel(cinema,filme,lugar):
    res = True
    for sala in cinema:
        if sala[2] == filme:
            for pontrona in sala[1]:
             if pontrona == lugar:
                res = False
    return res

#3. `vendebilhete( cinema, filme, lugar )` - que dá como resultado um novo cinema resultante de acrescentar o lugar à lista dos lugares ocupados, na sala onde está a ser exibido o filme;

def vendebilhete(cinema,filme,lugar):
    for sala in cinema:
        if sala[2] == filme:
            sala[1].append(lugar)
    return cinema

#4. `listardisponibilidades( cinema )` - que, para um dado cinema, lista no monitor para cada sala, o filme que está a ser exibido e o total de lugares disponíveis nessa sala (número de lugares na sala menos o número de lugares ocupados);

def listardisponibilidades(cinema):
    i = 0
    while i <= len(cinema)-1:
     print(f"Sala{i+1}: {cinema[i][2]}, {cinema[i][0] - len(cinema[i][1])}")
     i = i + 1

#5. `inserirSala( cinema, sala )` - que acrescenta uma sala nova a um cinema (devendo verificar se a sala já existe);

def inserirSala(cinema,sala):
    if sala not in cinema:
        cinema.append(sala)
    else:
        print("A sala já existe.")

sala_nova = input("Desejas inserir uma sala nova? (sim/não): ").lower()

if sala_nova  == 'sim':
        capacidade = int(input("Insira capacidade: "))
        filme = input("Insira filme: ")
        sala_nova = (capacidade, [], filme)
        inserirSala(cinema, sala_nova)
        print("Nova sala adicionada com sucesso!")
    
        listardisponibilidades(cinema)

#6. Acrescente todas as outras funcionalidades que achar necessárias;

def pipoca():
    pipoca = input("Deseja pipoca? (sim/não): ").lower()
    if pipoca == 'sim':
        tamanho = input("Qual tamanho? (pequena, média ou grande): ").lower()
        if tamanho == 'pequena':
            print("Você pediu uma pipoca pequena.")
        elif tamanho == 'média':
            print("Você pediu uma pipoca média.")
        elif tamanho == 'grande':
            print("Você pediu uma pipoca grande.")
```


```python 
  import CinemaApp as c

resposta = input("Você deseja aceder a aplicação para cinemas?(sim/não)").lower()
if resposta == "sim":
    sala1 = ( 120,[],"Lavagante" )
    sala2 = (90,[],"Uma Grande, Corajosa e Bela Viagem" )
    sala3 = (150,[],"The Conjuring 4: Extrema-Unção" )
    sala4 = (100,["A1", "A2", "A3", "A4", "A5", "A6", "A7", "A8", "A9", "A10", "B1", "B2", "B3", "B4", "B5", "B6", "I10", "J1", "J2", "J3", "J4", "J5", "J6", "J7", "J8", "J9", "J10"],"Batalha Atrás de Batalha" )
    sala5 = (130,[],"Demon Slayer: Castelo Infinito" )
    sala6 = (80,[],"The Smashing Machine: Coração de Lutador" )
    cinema = [sala1,sala2,sala3,sala4,sala5,sala6]
    
    while resposta != 0:
        print(""" Selecione uma opção:
         * (1) Filmes que estão em exibição 
         * (2) Disponibilidade do lugar
         * (3) Ocupar lugar
         * (4) Disponibilidade for sala
         * (5) Acrescentar sala nova
         * (6) Pedir pipoca""")
        
        resposta =input("Introduza o número da opção:")
        if resposta == "1":
            print(c.listar(cinema)) 
        elif resposta == "2":
            filme = input("Filme:")
            lugar = input("Lugar:")
            print(c.disponivel(cinema,filme,lugar))
        elif resposta == "3":
            print(c.vendebilhete(cinema,filme,lugar))
        elif resposta == "4":
            print(c.listardisponibilidades(cinema))
        elif resposta == "5":
            sala = input("Sala:")
            print(c.inserirSala(cinema,sala))
        elif resposta == "6":
            print(c.pipoca())
        else:
            print("Tchau! Até logo.")
            resposta = 0

else:
    print("Tchau! Até logo.")

```
