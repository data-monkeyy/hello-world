# Define the board

board = [['12:','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['11:','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['10:','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['9 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['8 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['7 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['6 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['5 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['4 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['3 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['2 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['1 :','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  ','  '],
         ['   ','1 ','2 ','3 ','4 ','5 ','6 ','7 ','8 ','9 ','10','11','12']]
	 	
# Run to print the board
for row in range(13):
    print(board[row])

# Read in the instructions into a list called instructions 
f = open("Route001.txt")
instructions = f.read().splitlines()

# Assign first two elements of instructions to a coordinate to get a starting point
b = int(instructions[0])
a = 12-int(instructions[1])
board[a][b] = 'x '

# Define a function that takes in N, E, S, W and produces a coordinate 
def instrct_to_coord(j):
    if j == 'N':
        print('coordinate is at (int(instructions[0]),int(instructions[1])+1)')
        board[a-1][b] = 'x '
        a = a - 1
    elif j == 'S':
        print('coordinate is at (int(instructions[0]),int(instructions[1])-1)')
        board[a+1][b] = 'x '
        a = a + 1
    elif j == 'E':
        print('coordinate is at (int(instructions[0])+1,int(instructions[1]))')
        board[a][b+1] = 'x '
        b = b + 1
    elif j == 'W':
        print('coordinate is at (int(instructions[0])-1,int(instructions[1]))')
        board[a][b-1] = 'x '
        b = b -1
    else:
        print('I do not understand this instruction')

# Action the instructions
for i in range(2,len(instructions)):
    instrct_to_coord(instructions[i])
