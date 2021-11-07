# A3-Interactive-Artwork

import tkinter as tk
import turtle
import random

penUp = True;

window = tk.Tk()
window.title("Drawing Board")
window.geometry("250x500")

def fwd():
    turtle.forward(10)

def back():
    turtle.backward(10)

def leftTurn():
    turtle.left(90)

def rightTurn():
    turtle.right(90)

def penSwitch():
    global penUp

    if(not penUp):
        turtle.penup()
        penUp = True
    else:
        turtle.pendown()
        penUp = False

        

b1 = tk.Button(text="forward", width=10, height=4, command=fwd).grid(row=0, column=1)
b2 = tk.Button(text="back", width=10, height=4, command=back).grid(row=2, column=1)
b3 = tk.Button(text="left", width=10, height=4, command=leftTurn).grid(row=1, column=0)
b4 = tk.Button(text="right", width=10, height=4, command=rightTurn).grid(row=1, column=2)
b5 = tk.Button(text="penup/down", width=10, height=4, command=penSwitch).grid(row=1, column=1)



colours = ('red', 'orange','yellow','green','blue','purple','pink')
tur = turtle.Turtle()



for x in range (5):
    randColour = random.randrange(0, len(colours)) #making it a random colour
    tur.color(colours[randColour], colours[random.randrange(0, len(colours))])
    #that second part is only needed if we want an outline
    rand1 = random.randrange(-300, 300)
    rand2 = random.randrange(-300, 300)
    tur.penup() #do this so the pen does not draw random lines
    tur.setpos((rand1, rand2)) #think of poitioning as being on a cartesian plane
    #rand1 and rand2 are the x and y coordinates
    tur.pendown()
    tur.begin_fill()
    tur.circle(random.randrange(0,80)) #getting different sized circles

    tur.end_fill()
    #now we have five random circles

import turtle
import random

def draw_retangle(x,y,w,h,color):
    turtle.up()
    turtle.seth(0)
    turtle.goto(x-w/2,y-h/2)
    turtle.fillcolor(color)
    turtle.down()
    turtle.begin_fill()
    for i in range(2):
        turtle.fd(w)
        turtle.left(90)
        turtle.fd(h)
        turtle.left(90)
    turtle.end_fill()

turtle.setup(700,700)
turtle.title("A3 Interactive Artwork")
turtle.speed(0)
turtle.hideturtle()
for i in range(5):
    draw_retangle(random.randint(-300,300),random.randint(-300,300),
                     random.randint(5,100),random.randint(5,100),
                     (random.uniform(0,1),random.uniform(0,1),random.uniform(0,1)))

def draw_triangle(w,x,y,h,color):
    turtle.up()
    turtle.seth(0)
    turtle.goto(x-w/2,y-h/2)
    turtle.fillcolor(color)
    turtle.down()
    turtle.begin_fill()
    for i in range(5):
        turtle.fd(x)
        turtle.left(60)
    turtle.end_fill()

turtle.speed(0)
turtle.hideturtle()
n = 100
for i in range(5):
    draw_triangle(random.randint(-100,100),random.randint(-100,100),
                     random.randint(5,50),random.randint(5,50),
                     (random.uniform(0,1),random.uniform(0,1),random.uniform(0,1)))


tur = turtle.Turtle()
tur.speed = (0)
tur.width(5) 

colours = ('red', 'orange','yellow','green','blue','black', 'purple', 'pink', 'light blue')


def up():
    tur.setheading(90)
    tur.forward(100)
    
def down():
    tur.setheading(270)
    tur.forward(100)
def left():
    tur.setheading(180)
    tur.forward(100)
def right():
    tur.setheading(0)#
    tur.forward(100)

def clickleft(x,y):
    tur.color(random.choice(colours))
def clickright(x,y):
    tur.stamp()
turtle.onscreenclick(clickleft, 1)
turtle.onscreenclick(clickright, 3)

turtle.listen() #starting an event
turtle.onkey(up, 'Up') #based on a key and it'll do the function
turtle.onkey(down, 'Down')
turtle.onkey(left, 'Left')
turtle.onkey(right, 'Right')


window.mainloop()

turtle.mainloop()
