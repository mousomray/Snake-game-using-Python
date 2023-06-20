# Snake game using Python in google colab 
Objective : Create snake game 

# I worked on this project 
* Importing the necessary modules
* Setting up the game board
* Initializing snake's initial position and size
* Initializing the food position
* Game loop
* Displaying the game board
* Getting user input for snake direction
* Updating snake position
* Checking for collision with food
* Updating snake body
* Checking for collision with walls or the snake's own body
* Ending the game

# Importing the necessary modules 
import random 
* The 'random' module is imported to generate random positions for the food.

# Setting up the game board
board_width = 20
board_height = 10
* These variables define the width and height of the game board.

# Initializing the food position and size 
snake_x = board_width // 2
snake_y = board_height // 2
snake_length = 1
snake_body = [(snake_x, snake_y)]
* The snake's initial position is set at the center of the game board. 'snake_length' represents the length of the snake, and 'snake_body' stores the coordinates of all segments of the snake's body.

# Initializing the food position 
food_x = random.randint(0, board_width - 1)
food_y = random.randint(0, board_height - 1)
* The food's initial position is randomly generated within the boundaries of the game board.

# Game loop 
game_over = False
while not game_over:
    ...
* The game loop continues until the 'game_over' variable becomes 'True'.

# Displaying the game board 
for y in range(board_height):
    for x in range(board_width):
        if (x, y) == (food_x, food_y):
            print('F', end=' ')
        elif (x, y) == snake_body[0]:
            print('H', end=' ')
        elif (x, y) in snake_body[1:]:
            print('S', end=' ')
        else:
            print('.', end=' ')
    print()
* This nested loop iterates over each position on the game board and prints the corresponding character for each element. 'F' represents 
 the food, 'H' represents the snake's head, 'S' represents the snake's body, and '.' represents an empty space.

# Getting user input for snake direction 
direction = input("Enter direction (up/down/left/right): ")
* The user is prompted to enter the 'direction' they want the snake to move in. The input is stored in the direction variable.

# Updating snake position 
if direction == 'up':
    snake_y -= 1
elif direction == 'down':
    snake_y += 1
elif direction == 'left':
    snake_x -= 1
elif direction == 'right':
    snake_x += 1
* Based on the user's input, the snake's position is updated accordingly.

# Checking for collision with food 
if (snake_x, snake_y) == (food_x, food_y):
    snake_length += 1
    food_x = random.randint(0, board_width - 1)
    food_y = random.randint(0, board_height - 1)
* If the snake's head collides with the food, the snake's length is increased by 1, and new random coordinates are 
 generated for the food.

# Updating snake body 
snake_body.insert(0, (snake_x, snake_y))
if len(snake_body) > snake_length:
    snake_body.pop()
* The snake's current head position is added to the 'snake_body' list. If the length of the snake exceeds the desired length, the last 
  segment of the snake's body is removed.

# Checking for collision with walls or the snake's own body 
if snake_x < 0 or snake_x >= board_width or snake_y < 0 or snake_y >= board_height or (snake_x, snake_y) in snake_body[1:]:
    game_over = True
* If the snake's head goes beyond the boundaries of the game board or collides with its own body, the 'game_over' variable is set to 
 'True', ending the game loop.

# Ending the game 
print("Game Over")
* Once the game loop ends, the "Game Over" message is printed.
 That's a step-by-step explanation of how this Snake game code works. It sets up the game board, handles user input, updates the snake's 
 position and length, checks for collisions, and ends the game when necessary.

