# Aplicação de Manipulação de Listas de Inteiros
## Autor: Isadora de Carvalho, A109413, foto
## Resumo: 
## Lista de resultados: links para os ficheiros da resolução

```python
#colocar no monitor o menu

def menu():
    print(""" Selecione uma opção:
    * (1) Criar Lista 
    * (2) Ler Lista
    * (3) Soma
    * (4) Média
    * (5) Maior
    * (6) Menor
    * (7) estaOrdenada por ordem crescente
    * (8) estaOrdenada por ordem decrescente
    * (9) Procura um elemento
    * (0) Sair""")

#Utilizador irá escolher uma das opções por meio do número 
#A aplicação executa a ação e depois apresenta de novo o menu 
#Se a opção for sair, a aplicação deverá terminar mostrando a lista que está nesse momento guardada.

#A aplicação terá uma variável interna que guarda a lista de números
ListaAtual = []

#Na opção 1, deverá ser criada uma lista de números aleatórios entre 1 e 100 que será guardada na variável interna;
# se a variável interna já tiver uma lista, esta será sobreposta/apagada pela nova lista;
def criarListaAleatória():
    import random 
    N = int(input("Introduza o número de elementos da lista: "))

    if ListaAtual != []:
        ListaAtual.clear()
        while N > 0:
            ListaAtual.append(random.randint(1,100))
            N = N - 1
    else:
        while N > 0:
            ListaAtual.append(random.randint(1,100))
            N = N - 1
    return ListaAtual
#Na opção 2, deverá ser criada uma lista com números introduzidos pelo utilizador, que será guardada na variável interna;
#se a variável interna já tiver uma lista, esta será sobreposta/apagada pela nova lista;

def criarListaInt():
    ListaAtual.clear()
    n = int(input("Introduza o número de elementos da lista: "))
    i = 1
    while len(ListaAtual) < n:
        elem = int(input("Introduza o elemento " + str(i) + ": "))
        ListaAtual.append(elem)
        i = i+1
    return ListaAtual




#Na opção 3, será calculada a soma dos elementos na lista no momento;

def somaLista():
    soma = 0
    for n in ListaAtual:
        soma += n
    return(soma)
        

#Na opção 4, será calculada a média dos elementos na lista no momento;

def medialista(ListaAtual):
    soma = 0
    for n in ListaAtual:
        soma += n 
    média = soma / len(ListaAtual)
    return(média)

#Na opção 5, será calculado o maior elemento da lista no momento;

def maiorelemento():
    res = ListaAtual[0] # a inicialização em zero não dá certo, precisa ser o primeiro número da lista 
    for elem in ListaAtual[1:]: # para n contar o primeiro elemento
        if elem > res: 
            res = elem
    return res #return fora do if


#Na opção 6, será calculado o menor elemento da lista no momento;

def menorelemento():
    res = ListaAtual[0] # a inicialização em zero não dá certo, precisa ser o primeiro número da lista 
    for elem in ListaAtual[1:]: # para n contar o primeiro elemento
        if elem < res: 
            res = elem
    return res

#Na opção 7, a aplicação deverá indicar (Sim/Não) se a lista está ordenada por ordem crescente;

def listacrescente(ListaAtual):
    for elem in range(len(ListaAtual)):
        if ListaAtual[elem] > ListaAtual[elem + 1]:
            return False
    return True

    


#Na opção 8, a aplicação deverá indicar (Sim/Não) se a lista está ordenada por ordem decrescente;
def listadecrescente(ListaAtual):
    for elem in range(len(ListaAtual)):
        if ListaAtual[elem] < ListaAtual[elem + 1]:
            return False
    return True


#Na opção 9, a aplicação irá procurar um elemento na lista, se o encontrar deverá devolver a sua 
# posição, devolverá -1 se o elemento não estiver na lista;

def posiçãolista():
    res = input ("Introduza o elemento que queres encontrar na lista: ")
    for elem in ListaAtual[0:]:
        if elem == res:
         return elem
        else:
            return "-1"
```

```python

 import ManipulaçãoDeApp as m

print("Você deseja aceder a aplicação para maniulação de listas de inteiros?(S/N)")
resposta = input("S/N")
if resposta == "S":
    ListaAtual = []
    while resposta != 0:
        print(""" Selecione uma opção:
         * (1) Criar Lista 
         * (2) Ler Lista
         * (3) Soma
         * (4) Média
         * (5) Maior
         * (6) Menor
         * (7) estaOrdenada por ordem crescente
         * (8) estaOrdenada por ordem decrescente
         * (9) Procura um elemento
         * (0) Sair""")
        resposta =input("Introduza o número da opção:")
        if resposta == "1":
            print(m.criarListaAleatória()) 
        elif resposta == "2":
            print(m.criarListaInt())
        elif resposta == "3":
            print(m.msomaLista())
        elif resposta == "4":
            print(m.medialista(ListaAtual))
        elif resposta == "5":
            print(m.maiorelemento())
        elif resposta == "6":
            print(m.menorelemento())
        elif resposta == "7":
            print(m.listacrescente(ListaAtual))
        elif resposta == "8":
            print(m.listadecrescente(ListaAtual))
        elif resposta == "9":
            print(m.posiçãolista())
        else:
            print("Tchau! Até logo.")
            resposta = 0

else:
    print("Tchau! Até logo.") ```
        
