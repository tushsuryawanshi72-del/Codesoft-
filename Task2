import math

# Initialize board
board = [" " for _ in range(9)]

# Print board
def print_board(board):
    for row in [board[i*3:(i+1)*3] for i in range(3)]:
        print("| " + " | ".join(row) + " |")

# Check for winner
def check_winner(board, player):
    win_conditions = [
        [0,1,2], [3,4,5], [6,7,8], # rows
        [0,3,6], [1,4,7], [2,5,8], # columns
        [0,4,8], [2,4,6]           # diagonals
    ]
    for cond in win_conditions:
        if board[cond[0]] == board[cond[1]] == board[cond[2]] == player:
            return True
    return False

# Check if board full
def is_full(board):
    return " " not in board

# Minimax algorithm
def minimax(board, depth, is_maximizing):
    if check_winner(board, "O"):
        return 1
    if check_winner(board, "X"):
        return -1
    if is_full(board):
        return 0

    if is_maximizing:  # AI turn (O)
        best_score = -math.inf
        for i in range(9):
            if board[i] == " ":
                board[i] = "O"
                score = minimax(board, depth + 1, False)
                board[i] = " "
                best_score = max(score, best_score)
        return best_score
    else:  # Human turn (X)
        best_score = math.inf
        for i in range(9):
            if board[i] == " ":
                board[i] = "X"
                score = minimax(board, depth + 1, True)
                board[i] = " "
                best_score = min(score, best_score)
        return best_score

# AI move
def ai_move(board):
    best_score = -math.inf
    move = 0
    for i in range(9):
        if board[i] == " ":
            board[i] = "O"
            score = minimax(board, 0, False)
            board[i] = " "
            if score > best_score:
                best_score = score
                move = i
    board[move] = "O"

# Main game loop
def play_game():
    print("Welcome to Tic-Tac-Toe! You are X, AI is O")
    print_board(board)

    while True:
        # Human move
        move = int(input("Enter your move (1-9): ")) - 1
        if board[move] != " ":
            print("Invalid move, try again!")
            continue
        board[move] = "X"

        if check_winner(board, "X"):
            print_board(board)
            print("🎉 You win!")
            break
        if is_full(board):
            print_board(board)
            print("It's a draw!")
            break

        # AI move
        ai_move(board)

        if check_winner(board, "O"):
            print_board(board)
            print("💻 AI wins!")
            break
        if is_full(board):
            print_board(board)
            print("It's a draw!")
            break

        print_board(board)

# Run the game
play_game()
