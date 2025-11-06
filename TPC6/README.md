# Título
## Autor: nome, id, foto
## Resumo: lista de parágrafos
## Lista de resultados: links para os ficheiros da resolução

```
tabMeteo1 = [((2022,1,20), 2, 16, 0),((2022,1,21), 1, 13, 0.2), ((2022,1,22), 7, 17, 0.01)]

def medias(tabMeteo):
    res = []
    for dia in tabMeteo:
        res.append((dia[0], (dia[1]+dia[2])/2))#criamos o tuplo
    return res

def guardaTabMeteo(t, fnome):
    #primeiro abrir o ficheiro

    f= open(fnome, "w", encoding= 'utf-8') #nome do ficheiro, modo de abertura
    for dia in t: # cada tuplo
        f.write(f"{dia[0][0]};{dia[0][1]};{dia[1]};{dia[2]};{dia[3]}\n") # \n tira espaços

    # por fim fecha o ficheiro
    f.close()

def carregaTabMeteo(fnome):
    #abrir
    f = open(fnome, encoding = 'utf-8')
    res = 0
    for linha in f: 
        campos = linha.split(";") # separar o que esta entre ;
        res.append(((int(campos[0]),int(campos[1]),int(campos[2]),float(campos[3]),float(campos[4]),float(campos[5]))))
    f.close()    
    return res

def minMin(tabMeteo):
    minima = tabMeteo[0][1]
    for dia in tabMeteo[1:]:
        if dia[0][1] < minima:
            minima = dia[0][1]
    return minima

def minMin2(tabMeteo):
    minima = tabMeteo[0][1]
    for data,tmin,tmax,prec in tabMeteo[1:]: #desmembrou o tuplo
        if tmin < minima:
            minima = tmin
    return minima

def amplTerm(tabMeteo):
    res = []
    for data,tmin,tmax,prec in tabMeteo[0:]:
        amp = int(tmax - tmin)
        res.append((data,amp))
    return res

def maxChuva(tabMeteo):
    maxima = tabMeteo[0][3]
    for data,tmin,tmax,prec in tabMeteo[0:]: #desmembrou o tuplo
        if prec > maxima:
            maxima = prec
    return (data,maxima)


def diasChuvosos(tabMeteo, p):
    res = []
    for data,tmin,tmax,prec in tabMeteo[0:]: #desmembrou o tuplo
        if prec > p:
            res.append((data,prec))
    return res

def maxPeriodoCalor(tabMeteo, p):
    res = []
    for data,tmin,tmax,prec in tabMeteo[0:]:
        if prec < p:
            res.append(data)
    return res

import matplotlib.pyplot as plt

# line 1 points
x1 = [1,2,3]
y1 = [2,4,1]
# plotting the line 1 points
plt.plot(x1, y1, label = "linha 1")
 
# line 2 points
x2 = [1,2,3]
y2 = [4,1,3]
# plotting the line 2 points
plt.plot(x2, y2, label = "linha 2")
 
# naming the x axis
plt.xlabel('Abcissas')
# naming the y axis
plt.ylabel('Ordenadas')
# giving a title to my graph
plt.title('Gráfico com duas funções')
 
# show a legend on the plot
plt.legend()
 
# function to show the plot
plt.show()

```

```
import MeterologiaApp as m

print("Você deseja aceder a aplicação de meterologia?(S/N)")
resposta = input("S/N")
if resposta == "S":
    tabMeteo1 = [((2022,1,20), 2, 16, 0),((2022,1,21), 1, 13, 0.2), ((2022,1,22), 7, 17, 0.01)]
    while resposta != 0:
        print(""" Selecione uma opção:
         * (1) Temperatura média
         * (2) Guardar tabela meterológica
         * (3) Carregar tabela meterológica
         * (4) Temperatura mínima
         * (5) Amplitude máxima
         * (6) Dia com maior precipitação
         * (7) Dias chuvosos em relção a precipitação desejada
         * (8) Maior número de dias consecutivos com precipitação abaixo da precipitação desejada
         * (9) Gráfico da temperatura mínima, máxima e de pluviosidade.
         * (0) Sair""")
        resposta =input("Introduza o número da opção:")
        if resposta == "1":
            print(m.medias(tabMeteo)) 
        elif resposta == "2":
            print(m.guardaTabMeteo(t, fnome))
        elif resposta == "3":
            print(m.carregaTabMeteo(fnome))
        elif resposta == "4":
            print(m.minMin(tabMeteo))
        elif resposta == "5":
            print(m.amplTerm(tabMeteo))
        elif resposta == "6":
            print(m.maxChuva(tabMeteo))
        elif resposta == "7":
            p = input("Precipitação desejada para a análise:")
            print(m.diasChuvosos(tabMeteo, p))
        elif resposta == "8":
            p = input("Precipitação desejada para a análise:")
            print(m.maxPeriodoCalor(tabMeteo, p))
        elif resposta == "9":
            import matplotlib.pyplot as plt

            # line 1 points
            x1 = [1,2,3]
            y1 = [2,4,1]
            # plotting the line 1 points
            plt.plot(x1, y1, label = "linha 1")
 
            # line 2 points
            x2 = [1,2,3]
            y2 = [4,1,3]
            # plotting the line 2 points
            plt.plot(x2, y2, label = "linha 2")
 
            # naming the x axis
            plt.xlabel('Abcissas')
            # naming the y axis    
            plt.ylabel('Ordenadas')
            # giving a title to my graph
            plt.title('Gráfico com duas funções')
 
            # show a legend on the plot
            plt.legend()
 
            # function to show the plot
            plt.show()
        else:
            print("Tchau! Até logo.")
            resposta = 0

else:
    print("Tchau! Até logo.")

```
