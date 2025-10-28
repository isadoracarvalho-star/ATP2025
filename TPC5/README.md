# Título
## Autor: nome, id, foto
## Resumo: lista de parágrafos
## Lista de resultados: links para os ficheiros da resolução

´´´ python 
# criar uma turma em modo lista que contenha os alunos em tuplo com seu nome, o id estudante e uma lista de 3 notas
def criar_turma():
    turma = []
    n = int(input("Insira o número de alunos da turma: "))
    for i in range(n):
        aluno = input("Insira o nome do aluno: ")
        id = input("Insira o id do aluno: ")
        notaTPC = input("Insira a nota do TPC do aluno: ")
        notaProj = input("Insira a nota do projeto do aluno: ")
        notaTeste = input("Insira a nota do teste do aluno: ")
        turma.append((aluno, id, [notaTPC, notaProj, notaTeste]))
    return turma

# inserir um aluno novo 
def inserir_aluno(turma):
    n = int(input("Insira o número de alunos a inserir: "))
    for i in range(n):
        aluno = input("Insira o nome do aluno: ")
        id = input("Insira o id do aluno: ")
        notaTPC = input("Insira a nota do TPC do aluno: ")
        notaProj = input("Insira a nota do projeto do aluno: ")
        notaTeste = input("Insira a nota do teste do aluno: ")
        turma.append((aluno, id, [notaTPC, notaProj, notaTeste]))
    return turma

#listar a turma
def listar_turma(turma):
    for aluno in turma:
        print(aluno[0])

#consultar um aluno pelo seu id
def consultar_aluno(turma):
    id = input("Insira o id do aluno a consultar: ")
    for aluno in turma:
        if aluno[1] == id:
            return aluno
        else:
            return "Aluno não encontrado"

#guardar a turma em um ficheiro 
def guardar_turma(turma):
  f = open("./ficheiros/turmaATP.csv", "a")
  for aluno in turma:
    f.write(aluno[0] + "," + aluno[1] + "," + str(aluno[2]) + "\n")
  f.close()

#carregar a turma de um ficheiro 
def carregar_turma():
    f = open("./ficheiros/turmaATP.csv", "r")
    print(f.read())
    f.close()
  ´´´

  ´´´ python 
  import GestãoAlunosApp as g

resposta = input("Você deseja aceder a aplicação para gestão de alunos?(sim/não)").lower()
if resposta == "sim":
    turma = []
    while resposta != 0:
        print("""- 1: Criar uma turma;
    - 2: Inserir um aluno na turma;
    - 3: Listar a turma;
    - 4: Consultar um aluno por id;
    - 8: Guardar a turma em ficheiro;
    - 9: Carregar uma turma dum ficheiro;
    - 0: Sair da aplicação""")
        
        resposta =input("Introduza o número da opção:")
        if resposta == "1":
            print(g.criar_turma()) 
        elif resposta == "2":
            print(g.inserir_aluno(turma))
        elif resposta == "3":
            print(g.listar_turma(turma))
        elif resposta == "4":
            print(g.consultar_aluno(turma))
        elif resposta == "5":
            print(g.guardar_turma(turma))
        elif resposta == "6":
            print(g.carregar_turma())
        else:
            print("Tchau! Até logo.")
            resposta = 0

else:
    print("Tchau! Até logo.")

´´´
