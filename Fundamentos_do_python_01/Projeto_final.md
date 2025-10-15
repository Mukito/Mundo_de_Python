from random import randrange
def display_board(board):
 # A função aceita um parâmetro contendo o status atual da placa
 # e o imprime no console.
    """
    Exibe o tabuleiro formatado no console.
    """
    print("+-------" * 3, "+", sep="")
    for row in range(3):
        print("|       " * 3, "|", sep="")
        for col in range(3):
            print("|   " + str(board[row][col]) + "   ", end="")
        print("|")
        print("|       " * 3, "|", sep="")
        print("+-------" * 3, "+", sep="")


def enter_move(board):
 # A função aceita o status atual do tabuleiro, pergunta ao usuário sobre sua jogada, 
 # verifica a entrada e atualiza o quadro de acordo com a decisão do usuário.
    """
    Pergunta ao usuário qual movimento deseja fazer, valida a entrada
    e atualiza o tabuleiro com o 'O'.
    """
    while True:
        move = input("Digite o número do campo (1-9): ")
        if not move.isdigit():
            print("❌ Entrada inválida! Digite um número entre 1 e 9.")
            continue
        move = int(move)
        if move < 1 or move > 9:
            print("❌ Fora do intervalo! Tente novamente.")
            continue

        row = (move - 1) // 3
        col = (move - 1) % 3

        if board[row][col] in ['O', 'X']:
            print("⚠️ Essa casa já está ocupada! Escolha outra.")
        else:
            board[row][col] = 'O'
            break

def make_list_of_free_fields(board):
 # A função navega pelo tabuleiro e constrói uma lista de todas as casas livres; 
 # a lista consiste em tuplas, enquanto cada tupla é um par de números de linha e coluna.
    """
    Retorna uma lista de tuplas (linha, coluna) das casas livres.
    """
    free = []
    for row in range(3):
        for col in range(3):
            if board[row][col] not in ['O', 'X']:
                free.append((row, col))
    return free

def victory_for(board, sign):
 # A função analisa o estado da placa a fim de verificar se 
 # o jogador usando 'O's ou 'X's ganhou o jogo
    """
    Verifica se o jogador (sign = 'X' ou 'O') venceu.
    """
    # Linhas
    for row in board:
        if all(cell == sign for cell in row):
            return True

    # Colunas
    for col in range(3):
        if all(board[row][col] == sign for row in range(3)):
            return True

    # Diagonais
    if all(board[i][i] == sign for i in range(3)) or all(board[i][2 - i] == sign for i in range(3)):
        return True

    return False
    
def draw_move(board):
 # A função desenha o movimento do computador e atualiza o tabuleiro.
    """
    O computador escolhe uma casa aleatória livre e marca com 'X'.
    """
    free = make_list_of_free_fields(board)
    if free:
        move = free[randrange(len(free))]
        board[move[0]][move[1]] = 'X'


# ======= Execução principal =======
board = [[1, 2, 3],
         [4, 5, 6],
         [7, 8, 9]]

# Agora o computador começa de forma aleatória
draw_move(board)

while True:
    display_board(board)
    if victory_for(board, 'X'):
        print("💻 O computador venceu!")
        break
    if not make_list_of_free_fields(board):
        print("🤝 Empate!")
        break

    enter_move(board)
    if victory_for(board, 'O'):
        display_board(board)
        print("🎉 Você venceu!")
        break
    if not make_list_of_free_fields(board):
        display_board(board)
        print("🤝 Empate!")
        break

    draw_move(board)
