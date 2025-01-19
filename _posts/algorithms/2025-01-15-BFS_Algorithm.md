---
layout: post
title:  "BFS_Algorithm"
date:   2025-01-15 22:48:10 +0900
categories: algorithms
---

### Algorithms - BFS  
What is BFS?  
Breadth-First Search  

By using FIFO queue, searching nodes for the manange.  
So it is literally, adding start node to the queue, and checks all the adjecent nodes. Load the unvisited nodes and check visited. Loop process.  

Time Complexity : O(V + E)
V: number of vertices(nodes).
E: number of edges(connections).


### Usage
It is used in shortest path findings.  
Whether the nodes are connected (checking).  
Solving puzzles that can be conected in all possible states.  
```
from collections import deque

def bfs(graph, start):
    queue = deque([start])
    visited = set([start])

    while queue:
        current = queue.popleft()
        print(f"Visiting: {current}")

        for neighbor in graph[current]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
           
graph = {
    'A': ['B', 'D'],
    'B': ['A', 'C', 'E'],
    'C': ['B'],
    'D': ['A'],
    'E': ['B']
}

bfs(graph, 'A')

```
```
A - B - C
|     \
D       E

```


### Example  

```
#13460
class Ball:
    def __init__(self, name, pos_x, pos_y, trace_mark):
        self.ball_type = name
        self.pos_x = pos_x
        self.pos_y = pos_y
        self.ball_go_in = 0
        self.trace_mark = trace_mark
    def move_pos(self, new_pos_x, new_pos_y):
        self.pos_x = new_pos_x
        self.pos_y = new_pos_y
    def check_ball_in_hole(self):
        return self.ball_go_in
    
class SharedList:
    def __init__(self, x, y):
        self.list = [[0 for _ in range(x)] for _ in range(y)]
        self.count = 0;
        self.x_max = x;
        self.y_max = y;
        self.red_ball = Ball('R', -1, -1, 'r')
        self.blue_ball = Ball('B', -1, -1, 'b')
        self.hole = Ball('O', -1, -1, 'o')
        
        
    def set_2d_list(self, row, temp_row):
        self.list[row] = temp_row
        if 'R' or 'B' or 'O' in temp_row:
            for col in range(self.x_max):
                if (temp_row[col] == 'R'):
                    self.red_ball.move_pos(col, row)
                elif (temp_row[col] == 'B'):
                    self.blue_ball.move_pos(col, row)
                elif (temp_row[col] == 'O'):
                    self.hole.move_pos(col, row)
        
    def move(self, ball, direction):
        dx, dy = direction
        
        # if dy == 0 right or left
        if (ball.check_ball_in_hole()):
            return
        
        elif (dx != 0):
            for i in range(self.x_max - 3):
                if (self.list[ball.pos_y][ball.pos_x + dx] == '.' or 
                    self.list[ball.pos_y][ball.pos_x + dx] == 'r' or 
                    self.list[ball.pos_y][ball.pos_x + dx] == 'b'):
                    self.list[ball.pos_y][ball.pos_x] = ball.trace_mark
                    ball.move_pos(ball.pos_x + dx, ball.pos_y)
                    self.list[ball.pos_y][ball.pos_x] = ball.ball_type
                    continue
                elif (self.list[ball.pos_y][ball.pos_x + dx] == 'O'):
                    self.list[ball.pos_y][ball.pos_x] = ball.trace_mark
                    ball.move_pos(ball.pos_x + dx, ball.pos_y)
                    ball.ball_go_in = 1
                    break
                else:
                    self.list[ball.pos_y][ball.pos_x] = ball.ball_type
                    break

        elif (dy != 0):
            for i in range(self.y_max - 3):
                if (self.list[ball.pos_y + dy][ball.pos_x] == '.' or 
                    self.list[ball.pos_y + dy][ball.pos_x] == 'r' or 
                    self.list[ball.pos_y + dy][ball.pos_x] == 'b'):
                    self.list[ball.pos_y][ball.pos_x] = ball.trace_mark
                    ball.move_pos(ball.pos_x, ball.pos_y + dy)
                    self.list[ball.pos_y][ball.pos_x] = ball.ball_type
                    continue
                elif (self.list[ball.pos_y + dy][ball.pos_x] == 'O'):
                    self.list[ball.pos_y][ball.pos_x] = ball.trace_mark
                    ball.move_pos(ball.pos_x, ball.pos_y + dy)
                    ball.ball_go_in = 1
                    break
                else:   
                    self.list[ball.pos_y][ball.pos_x] = ball.ball_type
                    break

        else:
            # print(f"Invalid direction: {direction}")
            return -1
        
    def turn_right(self):
        if (self.red_ball.pos_y == self.blue_ball.pos_y):
            if (self.red_ball.pos_x > self.blue_ball.pos_x):
                self.move(self.red_ball, (1, 0))
                self.move(self.blue_ball, (1, 0))
            else:
                self.move(self.blue_ball, (1, 0))
                self.move(self.red_ball, (1, 0))
        else:
            self.move(self.red_ball, (1, 0))
            self.move(self.blue_ball, (1, 0))
            
    def turn_left(self):
        if (self.red_ball.pos_y == self.blue_ball.pos_y):
            if (self.blue_ball.pos_x > self.red_ball.pos_x):
                self.move(self.red_ball, (-1, 0))
                self.move(self.blue_ball, (-1, 0))
            else:
                self.move(self.blue_ball, (-1, 0))
                self.move(self.red_ball, (-1, 0))
        else:
            self.move(self.red_ball, (-1, 0))
            self.move(self.blue_ball, (-1, 0))

    def turn_forward(self):
        if (self.red_ball.pos_x == self.blue_ball.pos_x):
            if (self.red_ball.pos_y > self.blue_ball.pos_y):
                self.move(self.red_ball, (0, 1))
                self.move(self.blue_ball, (0, 1))
            else:
                self.move(self.blue_ball, (0, 1))
                self.move(self.red_ball, (0, 1))
        else:
            self.move(self.red_ball, (0, 1))
            self.move(self.blue_ball, (0, 1))
            
    def turn_backward(self):
        if (self.red_ball.pos_x == self.blue_ball.pos_x):
            if (self.blue_ball.pos_y > self.red_ball.pos_y):
                self.move(self.red_ball, (0, -1))
                self.move(self.blue_ball, (0, -1))
            else:
                self.move(self.blue_ball, (0, -1))
                self.move(self.red_ball, (0, -1))
        else:
            self.move(self.red_ball, (0, -1))
            self.move(self.blue_ball, (0, -1))
        

def check_success(shared_list):
    # if (shared_list.red_ball.pos_x == shared_list.hole.pos_x and shared_list.red_ball.pos_y == shared_list.hole.pos_y):
    #     if (shared_list.blue_ball.pos_x == shared_list.hole.pos_x and shared_list.blue_ball.pos_y == shared_list.hole.pos_y):
    #         return 0
    #     else:
    #         return 1
    # else: 
    #     return 0
    if (shared_list.red_ball.check_ball_in_hole() == 1 and shared_list.blue_ball.check_ball_in_hole() == 0):
        return 1
    else:
        return 0
    
from collections import deque

def test(shared_list):
    max_moves = 10
    turns = [shared_list.turn_right, shared_list.turn_left, shared_list.turn_forward, shared_list.turn_backward]

    visited = set()
    queue = deque([(shared_list.list, shared_list.red_ball.pos_x, shared_list.red_ball.pos_y, 
                    shared_list.blue_ball.pos_x, shared_list.blue_ball.pos_y, shared_list.red_ball.ball_go_in, 
                    shared_list.blue_ball.ball_go_in, 0)])

    while queue:
        current_list, red_x, red_y, blue_x, blue_y, red_ball_in, blue_ball_in, move_count = queue.popleft()

        if move_count > max_moves:
            continue

        # Check if the current state is a success
        shared_list.list = [row[:] for row in current_list]
        shared_list.red_ball.move_pos(red_x, red_y)
        shared_list.blue_ball.move_pos(blue_x, blue_y)
        shared_list.red_ball.ball_go_in = red_ball_in
        shared_list.blue_ball.ball_go_in = blue_ball_in

        if check_success(shared_list) == 1:
            # print(shared_list.red_ball.pos_x, shared_list.red_ball.pos_y, shared_list.blue_ball.pos_x, shared_list.blue_ball.pos_y)
            # print(shared_list.red_ball.ball_go_in, shared_list.blue_ball.ball_go_in)
            # for row in shared_list.list:
            #     print("".join(row))

            return move_count

        # Generate next states
        for turn in turns:
            shared_list.list = [row[:] for row in current_list]
            shared_list.red_ball.move_pos(red_x, red_y)
            shared_list.blue_ball.move_pos(blue_x, blue_y)
            shared_list.red_ball.ball_go_in = red_ball_in
            shared_list.blue_ball.ball_go_in = blue_ball_in

            turn()

            new_state = (
                tuple(tuple(row) for row in shared_list.list),
                shared_list.red_ball.pos_x,
                shared_list.red_ball.pos_y,
                shared_list.blue_ball.pos_x,
                shared_list.blue_ball.pos_y,
                shared_list.red_ball.ball_go_in,
                shared_list.blue_ball.ball_go_in
            )

            if new_state not in visited:
                visited.add(new_state)
                queue.append((
                    [row[:] for row in shared_list.list],
                    shared_list.red_ball.pos_x,
                    shared_list.red_ball.pos_y,
                    shared_list.blue_ball.pos_x,
                    shared_list.blue_ball.pos_y,
                    shared_list.red_ball.ball_go_in,
                    shared_list.blue_ball.ball_go_in,
                    move_count + 1
                ))

    return -1

def mapping(shared_list):
    for row in range(shared_list.y_max):
        temp_row = input()
        shared_list.set_2d_list(row, list(temp_row))
    
def init():
    y, x = map(int, input().split())
    if (x < 3 or y > 10):
        # print("Invalid input")
        return
    shared_list = SharedList(x, y)
    return shared_list

def main():
    shared_list = init()
    mapping(shared_list)
    
    # print("Initial Map:")
    # for row in shared_list.list:
    #     print("".join(row))

    # # Print initial positions of the balls and hole
    # print(f"Red Ball: ({shared_list.red_ball.pos_x}, {shared_list.red_ball.pos_y})")
    # print(f"Blue Ball: ({shared_list.blue_ball.pos_x}, {shared_list.blue_ball.pos_y})")
    # print(f"Hole: ({shared_list.hole.pos_x}, {shared_list.hole.pos_y})")

    answer = test(shared_list)
    print(answer)
    
if __name__ == '__main__':
    main()
```