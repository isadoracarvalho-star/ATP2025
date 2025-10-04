# Título Jogo dos 21 fósforos
## Autor: Isadora de Carvalho, A109413, foto
## Resumo: Criar uma replica do jogo dos 21 fósforos, em que o usuário jogará contra o computador e quem ficar com o último fósforo perde
## Lista de resultados: links para os ficheiros da resolução

total = 21


print("""Bem-vindo ao jogo dos 21 fósforos! Seu Objetivo é escolher um número inteiro entre 1 a 4, 
      esse número será a quantidade de fósforos que vais tirar dos 21 existentes. Quem ficar com o 
      último fósforo perde """)
resposta = input("Vamos lá?(s/n)")

if resposta == "s":
    resposta = input("Queres começar?(s/n)")
     
    if resposta == "s":
        while total > 1:
            jogada = int(input("Quantos fósforos queres tirar? 1, 2 ,3 ou 4?"))
            total = total - jogada
            print( total - jogada)
            if  jogada == 1:
                print(total - 4)
                total = total - 4
            elif jogada == 2:
                print(total - 3 )
                total = total - 3 
            elif jogada == 3:
                print(total - 2)
                total = total - 2
            else:
                print(total - 1)
                total = total - 1
            if total == 1:
                print("Você perdeu!")
            if jogada != 1 or jogada != 2 or jogada != 3 or jogada != 4:
                total = -1
                print("Selecione um número válido de jogadas")
    else: 
         print("Okay, eu começo!")
         print(21-1)
        
         jogada = int(input("Quantos fósforos queres tirar? 1, 2 ,3 ou 4?"))
         print( 20 - jogada)
         computador = 1
         total = 20 - jogada
         
         while total >= 0:
            if jogada != 1 or jogada != 2 or jogada != 3 or jogada != 4:
                total = -1
                print("Selecione um número válido de jogadas")
            
            elif total == 1:
               total = -1
               print("Você ganhou!")
                 
            elif total == 0:
                total = -1
                print("Você perdeu!")
                 
            
            elif computador + jogada == 5:
                import random
                computador = random.randint(1,4)
                if total - computador < 0: 
                   total = -1
                   print("você ganhou!")
                    

                print(total - computador)
                total = total - computador
                jogada = int(input("Quantos fósforos queres tirar? 1, 2 ,3 ou 4?"))
                print( total - jogada)
                total = total - jogada
            else:
                if  jogada == 1:
                    print(total - 4)
                    total = total - 4
                    jogada = int(input("Quantos fósforos queres tirar? 1, 2 ,3 ou 4?"))
                    print( total - jogada)
                    total = total - jogada
                    if total == 0:
                        total = -1
                        print("Você perdeu!")
                        
                    if total == 1:
                        total = -1
                        print("Você ganhou!")
                         
                elif jogada == 2:
                    print(total - 3 )
                    total = total - 3
                    jogada = int(input("Quantos fósforos queres tirar? 1, 2 ,3 ou 4?"))
                    print( total - jogada)
                    total = total - jogada
                    if total == 0:
                        total = -1
                        print("Você perdeu!")
                            
                    if total == 1:
                        total = -1
                        print("Você ganhou!")
                            
                elif jogada == 3:
                    print(total - 2)
                    total = total - 2
                    jogada = int(input("Quantos fósforos queres tirar? 1, 2 ,3 ou 4?"))
                    print( total - jogada)
                    total = total - jogada
                    if total == 0:
                        total = -1
                        print("Você perdeu!")
                        
                    if total == 1:
                        total = -1
                        print("Você ganhou!")
                        
                else:
                    print(total - 1)
                    total = total - 1
                    jogada = int(input("Quantos fósforos queres tirar? 1, 2 ,3 ou 4?"))
                    print( total - jogada)
                    total = total - jogada
                    if total == 0:
                        total = -1
                        print("Você perdeu!")
                        
                    if total == 1:
                        total = -1
                        print("Você ganhou!")
                        
else:
    print("Tudo bem, até logo!")
