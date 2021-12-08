# CVaz-Geek-Gurl-Snowflakes
Additional Snowflake designs
# Geek Gurl Diaries Episode 33: Xmas Special Make Snowflakes with Turtle
# By Carrie Anne Philbin
# https://www.youtube.com/watch?v=DHmeX7YTHBY

import turtle
import random

# setup the window with a background colour
wn = turtle.Screen()
wn.bgcolor("cyan")

# assign a name to your turtle
cvaz = turtle.Turtle()
cvaz.speed(0)

# create a list of colours
sfcolor = ["white", "blue", "purple", "grey", "magenta"]

# create a function to create different size snowflakes
def snowflake(size):
# move the pen into starting position
    cvaz.penup()
    cvaz.forward(10*size)
    cvaz.left(45)
    cvaz.pendown()
    cvaz.color(random.choice(sfcolor))
    # draw branch 8 times to make a snowflake
    for i in range(8):
        branch(size)   
        cvaz.left(45)
    

# create one branch of the snowflake
def branch(size):
    for i in range(3):
        for i in range(3):
            cvaz.forward(10.0*size/3)
            cvaz.backward(10.0*size/3)
            cvaz.right(45)
        cvaz.left(90)
        cvaz.backward(10.0*size/3)
        cvaz.left(45)
    cvaz.right(90) 
    cvaz.forward(10.0*size)

# loop to create 20 different sized snowflakes with different starting co-ordinates
for i in range(20):
    x = random.randint(-200, 200)
    y = random.randint(-200, 200)
    sf_size = random.randint(1, 4)
    cvaz.penup()
    cvaz.goto(x, y)
    cvaz.pendown()
    snowflake(sf_size)

# leave the window open until you click to close  
wn.exitonclick()  
