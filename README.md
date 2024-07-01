# snake_game
# Create Snake Game in Python – Snake Game Program using Pygame
# Objective
The objective of this project is to implement the snake game using  Python. It requires a specific module pygame to start building the game. You also need to import pygame and random modules. Knowledge of  Python functions and loops is required.
# Project File structure
Steps to follow to built snake game in python:

Installing Pygame
Importing random and Pygame
Creating the game window
Displaying score on the screen
To make the welcome screen
Defining the variables that will be used in the program
If the game is over
To play the game with the help of arrow keys
Eating the food and displaying score
Increasing the length of  snake
If the snake collides with itself or the wall
Plotting the  snake
# Installing Pygame:
pip install Pygame
# Importing random and Pygame:
import pygame
import random
# Creating the  snake game window:
x = pygame.init()
width_of_screen = 900
height_of_screen = 600
gameWindow = pygame.display.set_mode((width_of_screen,height_of_screen))
pygame.display.set_caption("python snake game PythonGeeks")
pygame.display.update()
clock = pygame.time.Clock()
# Displaying  snake game score on the screen:
def score_on_screen(text,color,x,y):
    screen_text = font.render(text, True , color)
    gameWindow.blit(screen_text,[x,y])
# To make the welcome screen:
def welcome():
    game_exit = False
    while not game_exit:
        gameWindow.fill((255,182,193))
        score_on_screen("Welcome to snakes game by PythonGeeks",black,90,250)
        score_on_screen("Press spacebar to play",black,232,290)
        for event in pygame.event.get():
            if event.type==pygame.QUIT:
                game_exit = True
            if event.type==pygame.KEYDOWN:
                if event.key==pygame.K_SPACE:
                    game()
        pygame.display.update()
        clock.tick(60)
# Defining the variables that will be used in the program:
  def game():
    game_exit= False
    game_over= False
    snake_x=45
    snake_y=55
    velocity_x= 0
    velocity_y= 0
    init_velocity = 5
    score= 0
    apple_x = random.randint(20,width_of_screen/2)
    apple_y = random.randint(20,height_of_screen/2)
    snake_size=30
    snake_list = []
    snake_length = 1
    fps=40
# If the snake game is over:
with open ("highscore.txt","r") as f:
        highscore = f.read()
    while not game_exit:
        if game_over:
            with open ("high score.txt","w") as f:
                f.write(str(highscore))
            gameWindow.fill(white)
            score_on_screen("Game Over! Press Enter to continue",red,100,250)
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    game_exit = True
                if event.type== pygame.KEYDOWN:
                    if event.key == pygame.K_RETURN:
                        welcome()
# To play the  snake game with the help of arrow keys:
else:
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    game_exit = True
                if event.type==pygame.KEYDOWN:
                    if event.key == pygame.K_RIGHT:
                        velocity_x =  init_velocity
                        velocity_y = 0
                    if event.key == pygame.K_LEFT:
                        velocity_x = -init_velocity
                        velocity_y = 0
                    if event.key == pygame.K_UP:
                        velocity_y = -init_velocity
                        velocity_x = 0
                    if event.key == pygame.K_DOWN:
                        velocity_y =  init_velocity
                        velocity_x = 0
            snake_x+=velocity_x
            snake_y+=velocity_y
# Eating the food and displaying score:
  if abs(snake_x - apple_x)<20 and abs(snake_y - apple_y)<20:
                score+=10
                apple_x = random.randint(20,width_of_screen/2)
                apple_y = random.randint(20,height_of_screen/2)
                snake_length+=5
                if score>int(highscore):
                    highscore = score
            gameWindow.fill(white)
            score_on_screen("Score: "+str(score) + " highscore: "+str(highscore),red,5,5)
            pygame.draw.rect(gameWindow,red,[apple_x,apple_y,snake_size,snake_size])
# Increasing the length of snake:
head=[]
            head.append(snake_x)
            head.append(snake_y)
            snake_list.append(head)
            if len(snake_list)>snake_length:
                del snake_list[0]
# If the  snake collides with itself or the wall:
if head in snake_list[:-1]:
                game_over=True
if snake_x<0 or snake_x>width_of_screen or snake_y<0 or snake_y>height_of_screen:
                game_over = True
# Plotting the snake:
def plot_snake(gameWindow, color ,snake_list,snake_size):
    for x,y in snake_list:
        pygame.draw.rect(gameWindow,color,[x,y,snake_size,snake_size])
# Remaining code:
plot_snake(gameWindow,black,snake_list,snake_size)
            pygame.draw.rect(gameWindow,black,[snake_x,snake_y,snake_size,snake_size])
        pygame.display.update() 
        clock.tick(fps)
    pygame.quit()
    quit()
welcome()
![image](https://github.com/RajRishiUppal001/snake_game/assets/174259057/705bdbc6-7723-4614-a018-1eb830e87900)
# Summary
We have successfully developed a  snake game in  python. We have used pygame to create  snake game. We have created various functions to play the game.
