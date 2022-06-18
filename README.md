import time

table = [1, 2, 3, 4, 5, 6, 7, 8, 9]
run = True
winningTable = 0


def welcome():
    global start1
    print()
    print("Welcome to Tic Tac Toe game!!!")
    time.sleep(1)
    start1 = input("Do you want to start the game: ")

welcome()


def showTable():
    print()
    print(table[0], "|", table[1], "|", table[2])
    print("---------")
    print(table[3], "|", table[4], "|",table[5])
    print("---------")
    print(table[6], "|", table[7], "|", table[8])
    print()

def checkWinX(x):
    if (table[0] and table[1] and table[2]) or (table[4] and table[5] and table[6]) or (table[7] and table[8] and table[9]) or (table[1] and table[4] and table[7]) or (table[2] and table[5] and table[8]) or (table[3] and table[6] and table[9]) or (table[2] and table[5] and table[9]) or (table[4] and table[5] and table[7]) == x:
        run = False
        print("X win")

def checkWin0(o):
    if (table[0] and table[1] and table[2]) or (table[4] and table[5] and table[6]) or (table[7] and table[8] and table[9]) or (table[1] and table[4] and table[7]) or (table[2] and table[5] and table[8]) or (table[3] and table[6] and table[9]) or (table[2] and table[5] and table[9]) or (table[4] and table[5] and table[7]) == o:
        run = False
        print("0 win")

def gameProcess():
    start = start1.strip()
    start = start1.lower()
    start = start1.title()
    if start == "Yes":
        showTable()

        XorY = input("What do you want to be X or 0: ")
        XorY = XorY.upper()
        if XorY == "X":
            while run:
                number1 = int(input("Write a number to fill a box with X: "))
                print(number1)
                if number1 in table:
                    number1 -= 1
                    table[number1] = "X"
                    showTable()
                    print(table)
                    checkWinX("X")
                
                else:
                    print()
                    print("Error, type a number that is in the table!!!")
                    print()
                    continue  

                number2 = int(input("Write a number to fill a box with 0: "))
                if number2 in table:
                    number2 -= 1
                    table[number2] = "0"
                    showTable()
                    print(table)
                    checkWin0("0")

                else:
                    print()
                    print("Error, type a number that is in the table!!!")
                    print()
                    continue

gameProcess()
