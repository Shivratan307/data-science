# data-science
codes related to data science
from itertools import permutations, combinations
chess_size = 8
n = int(chess_size)
x = range(0, n)

def is_diagonally_present(point1, point2):
    x1 = point1[0]
    y1 = point1[1]
    x2 = point2[0]
    y2 = point2[1]
    gradient = (y2-y1)/(x2-x1)
    if gradient == -1 or gradient == 1:
        return(True)
    else:
        return(False)

list_of_permutations = []

for permuation in permutations(range(0, n)):
    y = permuation
    all_permutations = list(zip(x,y))
    list_of_permutations.append(all_permutations)

for possible_solution in list_of_permutations:
    solutions = []
    for piece1, piece2 in combinations(possible_solution, 2):
        solutions.append(is_diagonally_present(piece1, piece2))

    if True not in solutions:
        break
final_solution= []
for i in range(len(possible_solution)):
  for j in range(len(possible_solution[i])):
     final_solution.append(possible_solution[i][1])
     break
print(final_solution)
