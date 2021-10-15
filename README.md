# Sudoku-Game
import numpy as np
grid = [[5,3,0,0,7,0,0,0,0],[6,0,0,1,9,5,0,0,0],[0,9,8,0,0,0,0,6,0],[8,0,0,0,6,0,0,0,3],[4,0,0,8,0,3,0,0,1],[7,0,0,0,2,0,0,0,6],[0,6,0,0,0,0,2,8,0],[0,0,0,4,1,9,0,0,5],[0,0,0,0,8,0,0,0,0]]


def possibilities (row,column,number):
  global grid
  for i in range (9):
    if grid [row][i] == number:
      return false
  for i in range (9):
    if grid [i][column]==number:
      return false
  x0= (cloumn//3)*3
  y0=(row//3)*3
  for i in range (3):
    for j in range (3):
      if grid[y0+i][x0+j]==number:
        return false
  return true
def solve():
  global grid
  for row in range (9):
    for column in range (9):
      if grid[row][column]==number:
        for number in range (1,10):
          if possibilities (row,column,number):
            grid[row][column]=number
            solve()
            grid[row][column]=0
        return
print(np.matrix(grid))
