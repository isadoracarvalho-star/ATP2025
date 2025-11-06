# Título
## Autor: nome, id, foto
## Resumo: lista de parágrafos
## Lista de resultados: links para os ficheiros da resolução

```
#tpc-1
#a)
lista1 = [1, 2, 3, 4, 5]
lista2 = [4, 5, 6, 7, 8]  

def compararncomuns(lista1,lista2):
  ncomuns = []
  for i in lista1:
    if i not in lista2:
      ncomuns.append(i)
  for j in lista2: 
    if j not in lista1:
      ncomuns.append(j)
  return ncomuns
  
print(compararncomuns(lista1,lista2))
# Resultado esperado: [1,2,3,7,8]

#b)
texto = """Vivia há já não poucos anos algures num concelho do Ribatejo
    um pequeno lavrador e negociante de gado chamado Manuel Peres Vigário"""

def maisde3letras(texto):
    lista =[]
    palavras = texto.split() 
    for palavra in palavras: 
        if len(palavra)>3:
            lista.append(palavra)
    return lista

print(maisde3letras(texto))

#c)
lista = ['anaconda', 'burro', 'cavalo', 'macaco']
listaRes = [...]

def indice_valor(lista):
    listaRes = []
    for i in range(len(lista)):
        listaRes.append((i+1, lista[i])) # Corrected to append (index + 1, element)
    return listaRes

print(indice_valor(lista))

#tpc-2
#a)
def strCount(s, subs):
  count = 0
  for i in range(len(s) - len(subs) + 1):
    if s[i : i + len(subs)] == subs:
      count += 1
  return count

print(strCount("catcowcat", "cat"))
print(strCount("catcowcat", "cow")) 
print(strCount("catcowcat", "dog")) 

#b)
def produtoM3(lista):
    min1 = float('inf')
    min2 = float('inf')
    min3 = float('inf')

    for num in lista:
        if num < min1:
            min3 = min2
            min2 = min1
            min1 = num
        elif num < min2:
            min3 = min2
            min2 = num
        elif num < min3:
            min3 = num
            
    return min1 * min2 * min3

print(produtoM3([12,3,7,10,12,8,9]))

#c)
def reduxInt(n):
  while len(str(n)) > 1:
      i = str(n)
      sum(int(x) for x in i) 
      n = sum(int(x) for x in i)
  return  n
print(reduxInt(38))
print(reduxInt(777))

#d)
def myIndexOf(s1, s2):
    len_s1 = len(s1)
    len_s2 = len(s2)

    for i in range(len_s1 - len_s2 + 1):
        if s1[i:i + len_s2] == s2:
            return i
    return -1

print(myIndexOf("Hoje está um belo dia de sol!", "belo"))
print(myIndexOf("Hoje está um belo dia de sol!", "chuva"))

#tpc-3
#a)
def quantosPost(redeSocial):
    return len(redeSocial)

#b)
def postsAutor(redeSocial, autor):
 res = 0
 for post in redeSocial:
    if post['autor'] == autor:
        res += 1
 return res

#c)
def autores(redeSocial):
    autores = []
    for post in redeSocial:
        if post['autor'] not in autores:
            autores.append(post['autor'])
            autores.sort()
    return autores

#d)
def insPost(redeSocial, conteudo, autor, dataCriacao, comentarios):
    novoPost = {
        'id': f'p{len(redeSocial) + 1}',
        'conteudo': conteudo,
        'autor': autor,
        'dataCriacao': dataCriacao,
        'comentarios': comentarios
    }
    redeSocial.append(novoPost)
    return redeSocial

#e)
def remPost(redeSocial, id):
        for post in redeSocial:
            if post['id'] == id:
                redeSocial.remove(post)
                return redeSocial
        return None

#f)
import json 

def postsPorAutor(redeSocial):
    distribuicao = {}
    for post in redeSocial:
        autor = post['autor']
        distribuicao[autor] = distribuicao.get(autor, 0) + 1
    return distribuicao

result = postsPorAutor(MyFaceBook)
print(json.dumps(result, indent=2))

#g)
def comentadoPor(redeSocial, autor):
    comentado = []
    for post in redeSocial:
        for comentario in post['comentarios']:
            if comentario['autor'] == autor:
              comentado.append(post['id'])
    return comentado
```


