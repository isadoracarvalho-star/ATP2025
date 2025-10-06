# Título Jogo dos 21 fósforos
## Autor: Isadora de Carvalho, A109413, foto
## Resumo: Criar uma replica do jogo dos 21 fósforos, em que o usuário jogará contra o computador e quem ficar com o último fósforo perde
## Lista de resultados: links para os ficheiros da resolução

```python
total = 21

print("""Bem-vindo ao jogo dos 21 fósforos! Seu objetivo é escolher um número inteiro entre 1 a 4.
Quem ficar com o último fósforo perde.""")

resposta = input("Vamos lá? (s/n): ")

if resposta == "s":
    resposta = input("Queres começar? (s/n): ")
    if resposta == "s":
        while total > 1:
            print(f"Fósforos restantes: {total}")
            jogada = int(input("Quantos fósforos queres tirar? 1, 2, 3 ou 4? "))
            while jogada < 1 or jogada > 4 or jogada > total - 1:
                jogada = int(input("Jogada inválida. Escolha entre 1 e 4: "))
            total -= jogada
            if total == 1:
                print("Você perdeu!")
                break
            computador = 5 - jogada if total > 5 else min(4, total - 1)
            print(f"O computador tira {computador}")
            total -= computador
            if total == 1:
                print("Você ganhou!")
                break
    else:
        print("Okay, eu começo!")
        computador = 1
        total -= computador
        print(f"O computador tira {computador}")
        while total > 1:
            print(f"Fósforos restantes: {total}")
            jogada = int(input("Quantos fósforos queres tirar? 1, 2, 3 ou 4? "))
            while jogada < 1 or jogada > 4 or jogada > total - 1:
                jogada = int(input("Jogada inválida. Escolha entre 1 e 4: "))
            total -= jogada
            if total == 1:
                print("Você perdeu!")
                break
            computador = 5 - jogada if total > 5 else min(4, total - 1)
            print(f"O computador tira {computador}")
            total -= computador
            if total == 1:
                print("Você ganhou!")
                break
else:
    print("Tudo bem, até logo!")
```

