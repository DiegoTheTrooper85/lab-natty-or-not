# Título do Projeto Extremamente Aesthetic ;)

## 📒 Descrição
Como utilizar IA para aprender linguagem de programaçao

## 🤖 Tecnologias Utilizadas
COPILOT

## 🧐 Processo de Criação
O material foi gerado solicitando que o COPILOT verificasse erros no código apresentado, incialmente a linguagem era o C#, mas ao iniciar o estudo em PYTHON consegui ir um pouco além do que era proposto no Curso.

## 🚀 Resultados
# Entrada maior que zero
def input_maior_que_zero(mensagem, tipo):
    while True:
        try:
            valor = tipo(input(mensagem))
            if valor > 0:
                return valor
            else:
                print("O valor deve ser maior que zero.")
        except ValueError:
            print("O valor deve ser um número válido.")

# Entrada de Números que Aceitem Zero e Valores Negativos
def input_com_negativos(mensagem, tipo):
    while True:
        try:
            valor = tipo(input(mensagem))
            return valor
        except ValueError:
            print("O valor deve ser um número válido.")

# Declaração das matrizes
n = input_maior_que_zero("Qual a ordem das matrizes? ", int)
matA = [[0 for _ in range(n)] for _ in range(n)]
matB = [[0 for _ in range(n)] for _ in range(n)]

# Entrada de dados da matriz matA
print("Digite os dados da matriz A:")
for i in range(n):
    for j in range(n):
        matA[i][j] = input_com_negativos(f"Elemento [{i};{j}]: ", float)

# Somar números positivos da matriz e imprimir resultado
somaPositivos = 0
for i in range(n):
    for j in range(n):
        if matA[i][j] > 0:
            somaPositivos += matA[i][j]
print(f"\nSoma dos positivos = {somaPositivos:.1f}")
print("")

# Escolher uma linha da matriz e imprimir essa linha
linha = input_maior_que_zero("Escolha uma linha (0 a n-1): ", int)
if linha >= n:
    print("Linha inválida!")
else:
    print("Linha escolhida: ", end="")
    for j in range(n):
        print(f"{matA[linha][j]} ", end="")
    print("")
print("")

# Escolher uma coluna da matriz e imprimir essa coluna
coluna = input_maior_que_zero("Escolha uma coluna (0 a n-1): ", int)
if coluna >= n:
    print("Coluna inválida!")
else:
    print("Coluna escolhida: ", end="")
    for i in range(n):
        print(f"{matA[i][coluna]} ", end="")
    print("")
print()

# Imprimir a diagonal principal
print("Diagonal principal:")
for i in range(n):
    print(f"{matA[i][i]} ", end="")
print("")
print("")

#gerar matriz B
print("Matriz Alterada.")
for i in range(n):
    for j in range(n):
        if matA[i][j] < 0:
            matB[i][j] = matA[i][j]**2
        else:
            matB[i][j] = matA[i][j]

#imprimir matriz b
for i in range(n):
    for j in range(n):
        print(f"{matB[i][j]:.1f} ", end="")
    print("")

