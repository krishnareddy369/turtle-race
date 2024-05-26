Overview
The Turtle Race Game is an interactive Python program that simulates a race between six turtles. Players can place a bet on which turtle they think will win the race. Each turtle moves a random distance forward in each iteration, making the race unpredictable and exciting. The first turtle to cross the finish line wins the race.

Prerequisites
 -Python 3.x
-turtle module (comes standard with Python)
How to Run the Game
  1.Ensure you have Python 3.x installed on your system.
  2.Copy the provided code into a Python script file (e.g., turtle_race.py).
  3.Run the script using a Python interpreter.
sh
python turtle_race.py

How to Play
  1.When the game starts, a dialog box will appear prompting you to place your bet on which turtle will win the race. Enter the color of the turtle you think will win (options are: red, orange, yellow, green, blue, purple).
  2.After placing your bet, the race will start automatically.
  3.Watch the turtles race towards the finish line.
  4.Once a turtle crosses the finish line, the game will announce the winning turtle and whether your bet was correct.

Code Explanation
  -Imports and Screen Setup:

import turtle
from turtle import Turtle, Screen
import random

Initialize the race conditions and create the screen:

is_race_on = False
screen = Screen()
screen.setup(width=500, height=400)

Prompt the user for a bet:

user_bet = screen.textinput(title="Make your bet", prompt="Which turtle will win the race?")
Create turtles with different colors and positions:


colors = ["red", "orange", "yellow", "green", "blue", "purple"]
y_positions = [-70, -40, -10, 20, 50, 80]
all_turtles = []

for turtle_index in range(0, 6):
    new_turtle = Turtle(shape="turtle")
    new_turtle.color(colors[turtle_index])
    new_turtle.penup()
    new_turtle.goto(x=-230, y=y_positions[turtle_index])
    all_turtles.append(new_turtle)

    
Start the race if a bet is placed:


if user_bet:
    is_race_on = True

    
Race logic:

while is_race_on:
    for turtle in all_turtles:
        if turtle.xcor() > 230:
            is_race_on = False
            winning_color = turtle.pencolor()
            if winning_color == user_bet:
                print(f"You have won! The {winning_color} turtle is the winner.")
            else:
                print(f"You have lost. The {winning_color} turtle is the winner.")
        rand_distance = random.randint(0, 10)
        turtle.forward(rand_distance)
Exit on click:

screen.exitonclick()

Enjoy the Game!
Have fun betting on your favorite turtle and watching the exciting race!
